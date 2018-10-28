# WP Manual Image Crop

The plugin is a fork of Tomasz Sita's [WP Manual Image Crop](https://github.com/tomaszsita/wp-manual-image-crop) and merges many of its pull requests and provides additional enhancements.

**WP Manual Image Crop** allows you to manually crop all the image sizes registered in your WordPress theme (in particular the featured image).

Simply click on the "Crop" link next to any image in your media library. The "lightbox" style interface will be brought up and you are ready to go. Whole cropping process is really intuitive and simple.

Apart from media library list, the plugin adds links in few more places:

* Below featured image box ("Crop featured image")
* In the media insert modal window (once you select an image)

# Installation

* Download and install using the built in WordPress plugin installer.
* Activate in the "Plugins" area of your admin by clicking the "Activate" link.
* No further setup or configuration is necessary.

# API

## Filters

The plugin includes filters that can be used by other plugins:

#### `mic_do_crop`

Provides `$do_crop` (boolean), `$metadata` (array), and `$dims` (array). Returning false for `$do_crop` will prevent Manual Image Crop from cropping the image. `$metadata` contains the crop parameters, so another plugin can take over the actual cropping.

#### `mic_dst_file_path`

Provides `$path` (string) and `$data` (array). Manual Image Crop will write the new image to `$path` and save that path to the image metadata. `$data` contains the crop parameters that the user chose in WordPress admin.

#### `mic_dst_file_url`

Provides `$url` (string) and `$data` (array). Manual Image Crop will return `$url` in an AJAX response if the image crop is successful. `$data` contains the crop parameters that the user chose in WordPress admin.

The admin screen uses this URL to display the updated image. This URL is not stored with the image or used elsewhere in WordPress. `wp_get_attachment_image_src` is used instead to generate the image URL.

## Actions

The plugin includes actions that can be used by other plugins:

#### `mic_crop_done`

Triggered after a crop has been successfully completed, immediately before the JSON response is sent to the browser. Provides `$data` (array) and `$imageMetadata` (array).

# Translations

* Danish (Jan Francke-Larsen)
* Dutch (Bernardo Hulsman)
* French (Gabriel Féron)
* German (Bertram Greenhough)
* Hungarian (Roland Kal)
* Italian (Alessandro Curci)
* Polish (myself)
* Russian (Andrey Hohlov)
* Slovak (Patrik Benyak)
* Spanish (Andrew Kurtis)
* Swedish (Karl Oskar Mattsson)
