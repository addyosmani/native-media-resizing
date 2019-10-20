# Native Media Resizing Explainer

This proposal outlines a browser mechanism for offering native image resizing for user-uploaded images.

When uploading images to a site via the browser (e.g `<input type="file" accept="image/*">`) a user should be able to choose what size 
of image to upload. These options should include Original, Large, Medium, and Small. The browser should visualize the estimated file size of each option at the bottom of the display once an option has been selected.

The benefits of this capability are faster uploads of user-submitted images and data-savings from not sending overly large images over the network.

## Prior Art: Safari on iOS 13

In Safari for iOS 13, Apple [shipped](https://www.apple.com/ios/ios-13/features/) support for the above behavior. It allows a user to choose what size image to upload, providing
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

## Layering on top of File Input

This proposal does not require a developer to make any changes in order to benefit from browser-level image resizing. It builds on
top of the existing file input element and accept filter for indicating that you only want image files (`<input type="file" accept="image/*">`). This method works on all platforms. 

On desktop, browsers prompt the user to upload an image from the file system. In Chrome for Android and Safari on iOS, users are already provided an enhanced image selection experience (e.g the choice of which input method and app they would like to use to capture an image). Image resizing would build on this by extending mobile browsers to match Safari's behavior.

We may want to consider whether an attribute for developer opt-out is necessary, but this may not be required for MVP.

## User benefits

* Data-savings on upload: On mobile, uploading very high-resolution images can impact user's data-plans and the time it takes to upload the image before it can be used on a site. 
* Data-savings on download: A user who uploads a high-resolution image is relying on the site to figure out if the image should be resized and optimized. This is not always the case. Picture a user uploading a high-res photo as an avatar only for it to be served as-is from the site rather than a smaller version. Or, a CMS-user who is uploading stock photos for news articles.

## Future directions: Compression

In addition to native media resizing, native image compression could also be explored as a next-step. This would provide users the ability to locally compress their images to reduce their over-the-wire size. This could take the form of a simple quality slider that visualizes file size. Customizing optimizers (e.g MozJPEG) or formats (AV1) may be considered too advanced for the average user, but could also be considered in the future.

<img width="185" alt="Screen Shot 2019-10-20 at 1 51 51 PM" src="https://user-images.githubusercontent.com/110953/67166037-7cb0cf80-f37b-11e9-850c-5483be380d88.png">

