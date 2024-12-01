---
project: element-ui-el-table-draggable
stars: 111
description: Make 'el-table' of 'element UI' sortable.
url: https://github.com/WakuwakuP/element-ui-el-table-draggable
---

element-ui-el-table-draggable
=============================

Make 'el-table' of 'element UI' sortable.

Installation
------------

```
$ npm i -save element-ui-el-table-draggable
```

Quick Start
-----------

import ElTableDraggable from 'element-ui-el-table-draggable';

new Vue({
  components: {
    ElTableDraggable,
  },
});

<el-table-draggable\>
  <el-table\>
    ......
  </el-table\>
</el-table-draggable\>

Options
-------

### handle

Make a draggable part. You can drag only the specified class.

<el-table-draggable handle\=".handle"\>
  <el-table\>
    <el-table-column\>
      <template slot-scope\="scope"\>
        <div class\="handle"\>
          handle
        </div\>
      </template\>
    </el-table-column\>
    ......
  </el-table\>
</el-table-draggable\>

### animate

Specify animation speed (ms).

<el-table-draggable animate\="300"\>
  <el-table\>
    ......
  </el-table\>
</el-table-draggable\>

Contribution
------------

Please make sure to read the contributing guide (日本語 | English) before making a pull request.
