# Native Media Resizing Explainer

This proposal outlines a browser mechanism for offering native image resizing for user-uploaded images.

When uploading images to a site via the browser (e.g `<input type="file" accept="image/*">`) a user should be able to choose what size 
of image to upload. These options should include Original, Large, Medium, and Small. The browser should visualize the estimated file size of each option at the bottom of the display once an option has been selected.

The benefits of this capability are faster uploads of user-submitted images and data-savings from not sending overly large images over the network.

## Prior Art: Safari on iOS 13

In Safari for iOS 13, Apple shipped support for the above behavior. It allows a user to choose what size image to upload, providing
the options Actual Size, Large, Medium, and Small. File size information is summarized when a user selects one of these options.

![image-resize@2x](https://user-images.githubusercontent.com/110953/67166001-0d3ae000-f37b-11e9-8bed-20c493eea2c4.jpg)

The steps to use this functionality are as follows:

1. Go to a page with `<input type="file" accept="image/*">` (e.g https://imgbb.com/)
2. Select an option to upload an image 
3. Select Photo Library
4. Select an image from the library
5. Select "Choose Image Size" at the bottom of the screen
6. Select Large, Medium, Small, or Actual Size. Go back from the library.
7. Select 'Done' in the top-right corner of the screen to upload the image
