# Awesome Beaver Builder Extensions
Awesome Extensions for the [Beaver Builder](https://www.wpbeaverbuilder.com/) plugin for WordPress

## Table Of Contents
* [Modules](#modules)
* [Layouts](#layouts)
* [BB-friendly Themes](#beaver-builder-friendly-themes)
* [Add-on Plugins](#add-on-plugins)
* [Common Snippets](#common-snippets)

## Modules
Modules to add to your theme or plugin

* [SW PushMenu Module](http://fotoplugins.com/downloads/responsive-off-canvas-menu/)
* [SW Social Share Module](http://fotoplugins.com/downloads/sw-social-share/)
* [SW Responsive Tables Module](http://fotoplugins.com/downloads/sw-responsive-tables/)
* [SW Custom Footer Module](http://fotoplugins.com/downloads/sw-custom-footer/)
* [SW Countdown Module](http://fotoplugins.com/downloads/sw-countdown-module/)
* [SW PDF Viewer Module](http://fotoplugins.com/downloads/sw-pdf-viewer-module/)
* [SW Hover Card Module](http://fotoplugins.com/downloads/sw-hover-card-module/)
* [SW Tooltip Module](http://fotoplugins.com/downloads/swtooltip-module/)
* [SW Gallery Module](http://fotoplugins.com/downloads/sw-gallery-module/)

## Layouts
Have you designed a layout you'd like to share? Shoot me a link!

## Beaver Builder-friendly Themes
Know of a free or premium theme with great [Beaver Builder](wpbeaverbuilder.com) support? Send me the link!

## Custom Field Types
* [PDF Field Type](https://github.com/ZestSMS/BB-PDF-field)

## Add-On Plugins
* [Fotoplugins Modules Plugin](http://fotoplugins.com/downloads/fotoplugins-beaver-builder-modules/)
* [SW Beaver Builder Resizer](http://fotoplugins.com/downloads/sw-beaver-builder-resizer/)

## Common Snippets

How to check if a page is using a builder layout:
```php
<?php
// Include this function in functions.php of your theme.
function is_builder_layout() {
  if (class_exists( 'FLBuilderModel' ) && FLBuilderModel::is_builder_enabled()) return true;
  return false;
}

// Inside page.php I use is_builder_layout() to determine what kind of layout to display.
if (is_builder_layout()) {
  // big wide open edge-to-edge space for builder to use. Gives user the most options.
} else {
  // default page layout, two column w/ sidebar maybe? 
}
?>
```

Hope this was helpful! If you have suggestions for modules/layouts/themes/plugins/snippets feel free to send them to me as ticket or message me on the [Beaver Builder Slack team](http://beaverbuilders.slack.com) @brentjett!
