# fileViewer.js

> An extensive jQuery Plugin for rendering files

## Basic Usage

#### Declare a div target

```html
<div id="foo" data-file-name="myFile.jpg" data-file-path="content\myfile.jpg" data-file-contenttype="image/jpg"></div>
```

```js
$('#foo').fileViewer();
```

#### It is also possible to instantiate with many divs.


```html
<div class="bar" data-file-name="myFile.jpg" data-file-path="content\myfile.jpg" data-file-contenttype="image/jpg"></div>
<div class="bar" data-file-name="anotherFile.mp3" data-file-path="content\anotherFile.mp3" data-file-contenttype="audio/mpeg"></div>
...
...
```

```js
$('.bar').fileViewer();
```


## Advanced Options

All options can be informed by html attributes or parameters options method or defaults ($.fn.fileViewer.defaults).

```js
$('.bar').fileViewer(
    filePath: 'content\myfile.jpg',
    fileName: 'myFile.jpg', 
    fileExtension: '.jpg', //optional
    contentType: 'image/jpg', //optional: If a contentType a not filled, it will be discovered by fileExtension
    generateId: true //Sets the id to element render, e.g: id="pdf-viewer"
);
```

## Changing defaults

It is possible changes all parameters on fileViewer plugin, even viewers properties or viewers templates


## Adding new viewer support

First, we make the viewer object

```js
$.fn.fileViewer.defaults.viewers.cad = {
    id: 'cad-viewer',
    class: 'cad-viewer',
    render: function (file) {
        return ''; /*Add here a Cad template render*/
    }
}
```

After, we making the map for extension file to match the new viewer
```js
$.extend($.fn.fileViewer.defaults.map.extension, { '.dwg': 'cad'}) 
```

(Optional) Also, it is possible makes the map with contentType
```js
$.extend($.fn.fileViewer.defaults.map.contentType, { 'application/acad': 'cad'}) 
```

## Browser Support

This library passed on tests in the IE11 Browser.

## License

[MIT License](https://github.com/raafacachoeira/fileViewer.js/blob/master/LICENSE) © Rafael Cachoeira
