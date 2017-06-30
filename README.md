# Awesome Beaver Builder Extensions
Extensions for the awesome [Beaver Builder](https://www.wpbeaverbuilder.com/) page builder plugin for WordPress.

## Table Of Contents
* [Modules](#modules)
* [Custom Field Types](#custom-field-types)
* [Add-on Plugins and Libraries](#add-on-plugins--libraries)
* [Layouts](#layouts)
* [Beaver Builder Friendly Themes](#beaver-builder-friendly-themes)
* [Beaver Builder Child Themes](#beaver-builder-child-themes)
* [Beaver Builder Reference](#beaver-builder-reference)
* [Common Snippets](#common-snippets)

## Modules
Modules to add to your theme or plugin
* [ZestSMS Map](https://github.com/ZestSMS/BB-Override-Modules)
* [Beaver Builder Google Maps Module](https://github.com/thierrypigot/beaver-builder-googlemaps)
* [Custom Beaver Builder Icon Module](https://github.com/thierrypigot/bb-custom-icon-module)
* [Custom Module for Beaver Builder](https://github.com/bacoords/cb-custom-modules)
* [Timeline for Beaver Builder](https://wordpress.org/plugins/timeline-for-beaver-builder/)
* [Layout Module for Beaver Builder](https://github.com/thierrypigot/bb-layout)

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
* [Beaver Builder TinyMCE Advanced Icon Fix](https://wordpress.org/plugins/r3df-beaver-builder-tinymce-advanced-icon-fix/)
* [Beaver Builder Toolbox](https://github.com/thierrypigot/beaver-builder-toolbox)
* [Beaver Builder theme header manager](https://github.com/thierrypigot/beaver-builder-theme-header-manager)
* [Dashboard Welcome for Beaver Builder](https://wordpress.org/plugins/dashboard-welcome-for-beaver-builder/)
* [Template Widget for Beaver Builder](https://wordpress.org/plugins/template-widget-for-beaver-builder/)
* [Beaver Builder Templates for Genesis](https://github.com/crowdfavorite/bb-templates-genesis)
* [Column Separator for Beaver Builder](https://wordpress.org/plugins/column-separator-for-beaver-builder/)
* [Pods Beaver Themer Add-On](https://wordpress.org/plugins/pods-beaver-builder-themer-add-on/)
* [Genesis Dambuster](https://wordpress.org/plugins/genesis-dambuster/)
* [BB Delete cache](https://wordpress.org/plugins/bb-delete-cache/)
* [Beaverlodge Transparent Header](https://wordpress.org/plugins/beaverlodge-transparent-header/)
* [Beaverlodge Logout](https://wordpress.org/plugins/beaverlodge-logout/)
* [Fullwidth Templates for Any Theme & Page Builder](https://wordpress.org/plugins/fullwidth-templates/)
* [Beaver Builder Header Footer](https://wordpress.org/plugins/bb-header-footer/)
* [Beaver Builder Custom Dashboard Plugin](https://github.com/bluedognz/beaverbuilder-custom-dashboard)
* [Dynamic Template Switchboard for Beaver Builder](https://github.com/simbasounds/Dynamic-Template-Switchboard-for-Beaver-Builder-and-Dynamik)
* [Bootstrap Alerts For Beaver Builder](https://wordpress.org/plugins/bb-bootstrap-alerts/)
* [Expandable Row for Beaver Builder](https://wordpress.org/plugins/expandable-row-for-beaver-builder/)
* [WPD BB Additions](https://wordpress.org/plugins/wpd-bb-additions/)
* [Beaver Builder Peek-a-boo](https://wordpress.org/plugins/peek-a-boo-for-beaver-builder/)
* [BWPD Beaver Popups](https://wordpress.org/plugins/wpd-beaver-popups/)
* [Ninja Beaver Add-ons for Beaver Builder](https://wordpress.org/plugins/ninja-beaver-lite-addons-for-beaver-builder/)
* [FacetWP integration with Beaver Builder](https://github.com/FacetWP/facetwp-beaver-builder)
* [Addons for Beaver Builder](https://wordpress.org/plugins/addons-for-beaver-builder/)

## Layouts
Have you designed a layout you'd like to share? Shoot me a link!

## Beaver Builder friendly Themes
Know of a free or premium theme with great [Beaver Builder](http://www.wpbeaverbuilder.com) support? Send me the link!
* [GeneratePress](https://generatepress.com/)
* [OceanWP](https://oceanwp.org/)
* [Genesis](http://my.studiopress.com/themes/genesis/)
* [Actions](https://wordpress.org/themes/actions/)

## Beaver Builder Child Themes
* [GBeaver](http://gbeaver.com/)
* [Beaver Builder Child theme with Gulp](https://github.com/stephengreer08/bb-theme-child)
* [Beaver Builder Child Theme Generator](https://wpbeaveraddons.com/beaver-child-theme-generator/)

## Beaver Builder Reference
* [Beaver Builder Plugin Hooks](http://hooks.wpbeaverbuilder.com/bb-plugin/)
* [Beaver Themer Hooks](http://hooks.wpbeaverbuilder.com/bb-themer/)
* [Beaver Builder Theme Hooks](http://hooks.wpbeaverbuilder.com/bb-theme/)

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

Hope this was helpful.

For any missing resources, please add them as issues. https://github.com/lukecav/awesome-beaver-builder/issues
