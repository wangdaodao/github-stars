---
project: geo-three
stars: 847
description: Tile based geographic world map visualization library for threejs
url: https://github.com/tentone/geo-three
---

Geo-Three
=========

-   Library to display maps using `three.js`. Allows for full world-scale visualization of geographic data using tile-based chunks.
-   Can generate 3D geometry for terrain from terrain height data using software-generated tiles or using GPU displacement maps.
-   Supports multiple maps service providers (BingMaps, GoogleMaps, HereMaps, MapBox, MapTiler, OpenMapTiles, OpenStreetMaps).
    -   Each one of these map providers require a developer account and a API configuration to be used.
    -   It is possible to implement new providers using the `MapProvider` interface.
    -   Providers should have a tile-based map system to be supported by the library.

### Example

-   You can test some live demos of the library running from the project page.
-   Some of these examples might require API keys for the map services used.
    -   Sandbox
    -   Globe

### Usage

-   To add the library to your project get the library through NPM alongside with three.js and use it as a ES module.
-   You can also include the library directly in you webpage but ensure first that THREE is available globally.

// Create a map tiles provider object
var provider \= new OpenStreetMapsProvider();

// Create the map view and add it to your THREE scene
var map \= new MapView(MapView.PLANAR, provider);
scene.add(map);

// By default, coordinates are in meters. Resize to kilometers:
map.scale.set(0.001, 0.001, 0.001);

### Coordinates

-   The project internally uses a XY EPSG:900913 coordinate format to be compatible with the XYZ coordinates used in three.js
-   Use the `UnitsUtils` class to access the unit conversion methods. For example, to convert a latitude, longitude WGS84 pair value to XY coordinates you can use the code below:

var coords \= Geo.UnitsUtils.datumsToSpherical(40.940119, \-8.535589);
controls.target.set(coords.x, 0, \-coords.y);

### Tile Loading

-   Tiles are fetched from the service API configured. Each one of the services requires specific configuration using the specific `MapProvider` object.
    
-   Base tiles are always loaded at the beginning of the process. Each frame a couple of rays are cast into the tile tree. The number of rays can be configured using the `MapView` `subdivisionRays` attribute.
    
-   The distance of the ray to the camera is used to define if the node needs to simplified or sub-divided. These values can be configured using the `thresholdUp` and `thresholdDown` values.
    
    ​
    

### Data Providers

-   The library has support for multiple data providers that must be configured beforehand. Most of these data providers rely on an external API that differs from service to service.
    
-   Each one of them has its own provider object implementation of the `MapProvider` interface.
    
-   The `DebugProvider` doesn't show geographic imager, but instead shows the zoom level and the coordinates on each tile.
    

### LOD Control

-   The library includes multiple methods for LOD control, which define how tiles are subdivided or simplified.
    -   Raycast: Uses ray casting determine the distance of the nodes to the camera view. It only considers the nodes inside of the view frustum. This uses random sampling and takes some time to pick all nodes to be subdivided but is overall faster.
    -   Radial: Calculates the distance from the camera to each one of the nodes. The nodes closer are subdivided and nodes far away are simplified. This is a simple and effective method that considers all nodes, and provides a more consistent result.
    -   Frustum: Similar to the radial mode but only nodes inside of the view frustum are considered for subdivision.
-   Custom `LODControl` can be implemented by extending the `LODControl` object and implementing the `updateLOD(view, camera, renderer, scene)` method.

export class DistanceLOD extends LODControl
{
	constructor() {super();}

	updateLOD(view, camera, renderer, scene)
	{
        // Get world position of the camera.
        var pov \= new Vector3();
        camera.getWorldPosition(pov);

        view.traverse(function(node)
        {
            // Check if child in a MapNode
            if(node instanceof MapNode)
            {
                var position \= new Vector3();
                node.getWorldPosition(position);
				
                // Distance between camera and tile
                var distance \= pov.distanceTo(position);
                
                // Normalize distance based on tile level
                distance /= Math.pow(2, 20 \- node.level);
                
                // If closer than X subdivide
                if (distance < 50)
                {
                    node.subdivide();
                }
                // If far away, simplify parent
                else if (distance \> 200 node.parentNode)
                {
                    node.parentNode.simplify();
                }
            }
        });
	}
}

### Tiles Map Nodes

-   `MapNode` objects are used to define how the tiles should be represented in the space. Every node implements the `MapNode` class inheriting from the `THREE.Mesh` class (every map node has a visual representation as a mesh).
    -   `MapNode`s are organized hierarchically, where each node at zoom level N may have children at zoom level N+1.
-   The library has support for both planar and spherical representation of tiles. Most providers only have planar tiles available.
    -   It is required that the tiles for spherical mode are previously adjusted, since planar tiles get more stretched as closer you get to the poles.

-   There are available formats for GPU shader generated geometry using height data directly from the providers.
    -   GPU-generated geometry is more dense, more detailed and a lot faster. But the final geometry used is not accessible for ray casting, so interaction with these geometries is limited.

On the left, the geometry was generated in CPU. On the right, the geometry was displaced directly in the vertex shader:

### Custom Data Providers

-   It is possible to create new data providers to access other tile sources. New data sources have to provide access to the rasterized tile as a compatible DOM element (e.g. Image, Canvas, ...)
-   Custom providers have to extend the base `MapProvider` class and implement the `fetchTile(zoom, x, y)` method that returns a `Promise` with access to the tile data.
-   Below is an implementation of a provider to access OpenStreetMaps tile data using the Tile API. The provider simply loads the URL data into a image element.
-   These methods are called directly by nodes being loaded into the scene. These should be always asynchronous and should avoid any blocking actions.

export class OpenStreetMapsProvider extends MapProvider
{
	constructor(address) {super();}

	fetchTile(zoom, x, y)
	{
		return new Promise((resolve, reject) \=>
		{
			var image \= document.createElement("img");
			image.onload \= function(){resolve(image);};
			image.onerror \= function(){reject();};
			image.crossOrigin \= "Anonymous";
			image.src \= "https://a.tile.openstreetmap.org/" + zoom + "/" + x + "/" + y + ".png";
		});
	}
}

-   Tiles coordinates for each zoom level are counted from the left-top corner sequentially across the tiles.
-   Different API's might use different methods to index these tiles (e.g. Bing maps uses a different indexing method).
    -   These coordinates need to be adapted to ensure correct loading when using this library.

-   It is also possible to generate sythetic tiles, without any external API, by writing data directly into a canvas or even using a local image database to draw the map.
-   The code below shows how to implement a tile provider that draws a gradient from blue to red based on the zoom level of the tile with 16x16 pixels. This example can be used as basis for other code-based tile generators.

import {Color} from "three";

export class BlueToRedProvider extends MapProvider
{
	fetchTile(zoom, x, y)
	{
		const canvas \= new OffscreenCanvas(16, 16);
		const context \= canvas.getContext('2d');
		
		const blue \= new Color(0x0000FF);
		const red \= new Color(0xFF0000);
		const color \= blue.lerpHSL(red, (zoom \- this.minZoom) / (this.maxZoom \- this.minZoom));
		
		context.fillStyle \= color.getStyle();
		context.fillRect(0, 0, 16, 16);
		return Promise.resolve(canvas);
	}
}

### Custom Map Nodes

-   To implement a custom `MapNode`, we can create a new class that extends the base implementation.
-   The objects created from the class should then be passed as argument to the `MapView` object that is responsible for managing its life cycle.
-   All map nodes are based on three.js `Mesh` object and have attached a `Geometry` and `Material` used to render them into the scene.
-   These materials and geometries can be customized and are not required to be of any specific type. It is recommended to reuse them as much as possible to save memory.

import {SphereGeometry, MeshBasicMaterial, Vector3} from "three";

// The MapNode inherits from three Mesh object and requires a geometry and material
export class CustomMapNode extends MapNode
{
	constructor(parentNode \= null, mapView \= null, location \= MapNode.ROOT, level \= 0, x \= 0, y \= 0)
	{
		super(CustomMapNode.GEOMETRY, CustomMapNode.MATERIAL, parentNode, mapView, location, level, x, y);
	}
	
	static GEOMETRY \= new SphereGeometry(0.5, 32, 32); 
	
	static MATERIAL \= new MeshBasicMaterial();
	
	// Base geometry applied to the map view.
	static BASE\_GEOMETRY \= new MapNodeGeometry(1, 1, 1, 1);
	
	// Base scale is applied to the map view
	static BASE\_SCALE \= new Vector3(UnitsUtils.EARTH\_PERIMETER, 1, UnitsUtils.EARTH\_PERIMETER);

	initialize() {
		// Method to initialize data of the node (e.g fetch assets)
	}

	createChildNodes()
	{
		// Method called on subdivision to craete child nodes
	}
}

### License

-   Project uses a MIT license that allow for commercial usage of the platform without any cost.
-   The license is available on the project GitHub page
