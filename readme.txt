=== Manual Image Crop ===
Contributors: tomasz.sita, mcaskill
Tags: crop, cropping, thumbnail, featured image, gallery, images, picture, image, image area
Tested up to: 4.9.8
Requires at least: 4.0
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
Donate link: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=WB5ZQWGUM7T96
Stable tag: 1.13

Plugin allows you to manually crop all the image sizes registered in your WordPress theme (including the featured image).

== Description ==
Plugin allows you to manually crop all the image sizes registered in your WordPress theme (including the featured image).

Simply click on the "Crop" link next to any image in your media library.
The "lightbox" style interface will be brought up and you are ready to go.
Whole cropping process is really intuitive and simple.

Apart from media library list, the plugin adds links in few more places:
* Below featured image box ("Crop featured image")
* In the media insert modal window (once you select an image)

= Enjoying using Manual Image Crop? =
[Donate the plugin here](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=WB5ZQWGUM7T96 "Donate")

Thank you!

= GitHub Repository =
https://github.com/mcaskill/wp-manual-image-crop

= Translations =
* Danish (Jan Francke-Larsen)
* Dutch (Bernardo Hulsman)
* French (Gabriel Féron)
* German (Bertram Greenhough)
* Hungarian (Roland Kal)
* Italian (Alessandro Curci)
* Polish (Tomasz Sita, Maciej Gryniuk)
* Russian (Andrey Hohlov)
* Slovak (Patrik Benyak)
* Spanish (Andrew Kurtis)
* Swedish (Karl Oskar Mattsson)

Please contact me if you want to add a translation (or submit a pull request on GitHub)

== Installation ==
= Manually: =
*   Upload `manual-image-crop` to the `/wp-content/plugins/` directory
*   Activate the plugin through the 'Plugins' menu in WordPress

= Automatically: =
*   Navigate to the 'Plugins' menu inside of the wordpress wp-admin dashboard, and select AD NEW
*   Search for 'Manual Imag Crop', and click install
*   When the plugin has been installed, Click 'Activate'

== Filters ==
The plugin includes filters that can be used by other plugins:

=mic_do_crop=
Provides $do_crop (bool), $metadata (array), and $dims (array). Returning false for $do_crop will prevent Manual Image Crop from cropping the image. $metadata contains the crop parameters, so another plugin can take over the actual cropping.

=mic_dst_file_path=
Provides $path (string) and $data (array). Manual Image Crop will write the new image to $path and save that path to the image metadata. $data contains the crop parameters that the user chose in WordPress admin.

=mic_dst_file_url=
Provides $url (string) and $data (array). Manual Image Crop will return $url in an AJAX response if the image crop is successful. $data contains the crop parameters that the user chose in WordPress admin.

The admin screen uses this URL to display the updated image. This URL is not stored with the image or used elsewhere in WordPress. wp_get_attachment_image_src is used instead to generate the image URL.

== Actions ==
The plugin includes actions that can be used by other plugins:

= mic_crop_done =
Triggered after a crop has been successfully completed, immediately before the JSON response is sent to the browser. Provides $data (array) and $imageMetadata (array).

== Changelog ==
= 1.13 =
* Fixed thickbox bug where crop preview was scrolled off screen (WP 4.7)
* Filters added (Ryan DeBeasi)
* Action mic_crop_done added (Joey Line)
* Added warnings about conflicting plugins
* Removed distributed vendor packages and instead using versions included with WordPress
* Danish and Slovak translations added
* Polish translation updated
* Code cleanup

= 1.12.1 =
* Better handling of undersized images

= 1.12 =
* Fixed 'streched images' issue

= 1.11 =
* Hungarian translation added
* Swedish translation added
* Security improvements

= 1.10 =
* Fixed handling of array $crop param

= 1.09 =
* Dutch translation added
* Better error handling
* Fixed overwriting of previously saved crops
* Minor tweaks all around

= 1.08 =
* More descriptive error messages
* Russian translation added
* Hooked 'Crop' link to new media library layout (WP 4.0)
* A few minor edits

= 1.07 =
* Fixed 'Cannot use string offset as an array' error

= 1.06 =
* French, German, Italian, Polish, Spanish translations added
* Settings page added (quality, visibility, custom labels)
* Compatibility with Retina/HiDPI (@2x) plugin added
* Fixed issue with closing editor window from within media uploader screen

= 1.05 =
* WordPress 3.9 compatibility issues fixed
* Removed randomly floated 'Maximum upload file size'

= 1.04 =
* Added remembering of the previously selected area after cropping the specific image size
* Fixed the "wp_enqueue_script was called incorrectly" warning in the WP debug mode

= 1.03 =
* Fixed the issue with overwriting the original image when cropping image size registered after the attachment had been uploaded

= 1.02 =
* Fixed HTTP Authentication no preview issue
* Fixed path issues on multisite/subfolder WP installations

= 1.01 =
* Fixed Chrome stretched image issue
* Improved compatibility with other plugins using 'thickbox'

= 1.0 =
* Initial version
