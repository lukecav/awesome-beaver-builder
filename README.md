# Awesome Beaver Builder Extensions
Extensions for the awesome [Beaver Builder](https://www.wpbeaverbuilder.com/) plugin for WordPress

## Table Of Contents
* [Modules](#modules)
* [Custom Field Types](#custom-field-types)
* [Add-on Plugins](#add-on-plugins)
* [Layouts](#layouts)
* [BB-friendly Themes](#beaver-builder-friendly-themes)
* [Common Snippets](#common-snippets)

## Modules
Modules to add to your theme or plugin

* [ZestSMS Map](https://github.com/ZestSMS/BB-Override-Modules)
* [Beaver Builder Google Maps Module](https://github.com/thierrypigot/beaver-builder-googlemaps)

## Custom Field Types
These are additional settings field types to use in your custom modules.
* [PDF Field Type](https://github.com/ZestSMS/BB-PDF-field)
* [Date Picker](https://github.com/ZestSMS/BB-fields)
* [Location](https://github.com/ZestSMS/BB-fields)
* [Time Picker](https://github.com/ZestSMS/BB-fields)
* [Time Range](https://github.com/ZestSMS/BB-fields)
* [Post Select](https://github.com/ZestSMS/BB-fields)
* [Select2 Drop-Down](https://github.com/ZestSMS/BB-fields/tree/master/fields/select2)

## Add-On Plugins & Libraries
* [Beaverlodge Plugin](https://beaverlodgehq.com/downloads/beaverlodge-plugin/)
* [ZestSMS Field Types Bundle](https://github.com/ZestSMS/BB-fields)
* [BB Templates as Headers](https://github.com/jatacid/bb-template-as-header/)
* [Beaver Builder TinyMCE Advanced Icon Fix](https://github.com/r3df/r3df-beaver-builder-tinymce-advanced-icon-fix)
* [Beaver Builder Toolbox](https://github.com/thierrypigot/beaver-builder-toolbox)
* [Beaver Builder theme header manager](https://github.com/thierrypigot/beaver-builder-theme-header-manager)

Also see the Beaver Builder Team's [Recommended Plugins List](https://www.wpbeaverbuilder.com/knowledge-base/recommended-plugins/) for common helpful plugins that work well with Beaver Builder.

## Layouts
Have you designed a layout you'd like to share? Shoot me a link!

## Beaver Builder-friendly Themes
Know of a free or premium theme with great [Beaver Builder](http://www.wpbeaverbuilder.com) support? Send me the link!

## Common Snippets

How to check if a page is using a builder layout:
```php
<?php
// Include this function in functions.php of your theme.
function is_builder_layout() {
  if (class_exists( 'FLBuilderModel' ) && FLBuilderModel::is_builder_enabled()) return true;
  return false;
}

// Inside page.php, single.php, or singular.php use is_builder_layout() to determine what kind of layout to display.
if (is_builder_layout()) {
  // big wide open edge-to-edge space for builder to use.
} else {
  // default page layout, two column w/ sidebar maybe? Go nuts.
}
?>
```

How to default new pages to use Beaver Builder instead of the WordPress Editor.
```php
function make_beaver_builder_default_editor( $post_ID, $post, $update ) {

  // Enable BB Editor by default?
  $enabled = true;

  // On the first insert (not an update), set BB enabled to true.
  if (!$update) {
    update_post_meta( $post_ID, '_fl_builder_enabled', $enabled );
  }
}
add_action('wp_insert_post', 'make_beaver_builder_default_editor', 10, 3 );
```

There is also a nice collection of [CSS Snippets for the BB Plugin](https://www.wpbeaverbuilder.com/kb/css-snippets-plugin/) and [CSS Snippets for the BB Theme](https://www.wpbeaverbuilder.com/kb/css-snippets-theme/) on the [knowledge base](https://www.wpbeaverbuilder.com/knowledge-base/)

Hope this was helpful! If you have suggestions for modules/layouts/themes/plugins/snippets feel free to send them to me as ticket or message me on the [Beaver Builder Slack team](http://beaverbuilders.slack.com) @brentjett!
