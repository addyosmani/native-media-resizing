# Native Media Resizing Explainer

This proposal outlines a browser mechanism for offering native image resizing for user-uploaded images.

When uploading images to a site via the browser (e.g `<input type="file" accept="image/*">`) a user should be able to choose what size 
of image to upload. These options should include Original, Large, Medium, and Small. The browser should visualize the estimated file size of each option at the bottom of the display once an option has been selected.

The benefits of this capability are faster uploads of user-submitted images and data-savings from not sending overly large images over the network.
