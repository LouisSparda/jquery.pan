Fullscreen Image Zoom and Pan with Jquery
================================

Original 1.x version written by [Samir Hazir](https://github.com/saplumbaga/jquery.pan). Version 2.x written by me.

Fullscreen Image Zoom and Pan with Jquery

Features:

- Automatically add zoom and pan to any images or elements with images
- Auto-pan alongside pointer movement
- Zoom in and out support. You can increase or decrease the zoom level with specific buttons or with the mouse wheel
- Support for mobile devices. You can pan by dragging the zoomed image
- Support from IE8+ and modern desktop and mobile browsers

## Getting Started

Include jQuery and the plugin on a page and initialize the plugin. See a working demo at [https://jmalarcon.github.io/jquery.pan/](https://jmalarcon.github.io/jquery.pan/) or check the `index.html` page of this repository. You can also use it as a dependency with npm by simply writing:

```
npm i jquery.pan
```

Works with all versions of jQuery, from 1.x to the latest ones.

You must include a small CSS, `jquery.pan.css` in the `dist/css` folder (400b bytes gzipped).

```html
<link rel="stylesheet" href="css/jquery.pan.css" />
<script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
<script src="jquery.pan.js"></script>

<script type="text/javascript">
    $(function(){
        $(".pan").pan();
    })
</script>
```

If there's a `data-big` attribute in the element, then that URL will be used for the zoomed image. If there's not, then it should be an `<img>` element and the `src` attribute will be used to zoom the image, since a lot of images are limited in size to fit in their container (for example with the `max-width` property). Check out the `index.html` sample file in the repo.

```html
<a class="pan" data-big="img/big1.jpg" href="#"><img src="img/small1.jpg" alt="" ></a>
<img class="pan" style="max-width:150px;" src="img/big2.jpg" >
```

>**IMPORTANT**: It only adds the zoom capability to images that are **smaller than their natural size** or that have a `data-big` attribute, since small images don't need it. This is by design.

The `pan()` method filters out the jQuery selection and returns a jQuery selection with the final elements that have been processed to have zoom & pan capabilities. You can further process them as usual with jQuery, for example:

```javascript
$(function(){
    $(".mainContent img").pan().each(function() {
        $(this).attr('title', 'CLICK TO ZOOM');
    });
})
```


## License
Copyright (c) 2016 Samil Hazir, 2018 José M. Alarcon
Dual licensed under the GPL and MIT licenses.