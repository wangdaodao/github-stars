---
project: jpaginator
stars: 57
description: A JQuery plugin for pagination with a slider
url: https://github.com/remylab/jpaginator
---

Use this plugin with a unique element, don't forget the CSS page jPaginator.css.
Dependencies : jQuery 1.3.2+, jQuery UI Slider

New feature : Now you can reset the options with this snippet : $("#test1").trigger("reset",{nbPages:200,selectedPage:50})

Demo page : https://remylab.github.io/jpaginator/

Code sample :

$("#test1").jPaginator({
  nbPages:54,
  overBtnLeft:'#test1\_o\_left',
  overBtnRight:'#test1\_o\_right',
  maxBtnLeft:'#test1\_m\_left',
  maxBtnRight:'#test1\_m\_right',
  onPageClicked: function(a,num) {
      $("#page1").html("demo1 - page : "+num);
  }
});

The HTML :

  <div id="test1">

      <!-- optional left control buttons-->
      <a id="test1\_m\_left"></a><div id="test1\_o\_left"></div>

      <div class='paginator\_p\_wrap'>
        <div class='paginator\_p\_bloc'>
          <!--<a class='paginator\_p'></a> // page number : dynamically added -->
        </div>
      </div>

      <!-- optional right control buttons-->
      <div id="test1\_o\_right"></div><a id="test1\_m\_right"></a>


      <!-- slider -->
      <div class='paginator\_slider' class='ui-slider ui-slider-horizontal ui-widget ui-widget-content ui-corner-all'>
        <a class='ui-slider-handle ui-state-default ui-corner-all' href='#'></a>
      </div>

  </div>
