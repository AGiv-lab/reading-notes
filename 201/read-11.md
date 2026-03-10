# 201-Reading_11

##  Audio and Video in HTML; Domain Modeling Revisited

[Video and Audio Content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content){:target="_blank"}

1. Explain how the ability to use video and audio on the web has evolved since the early 2000s.
2. Describe the use of the `src` and `controls` attributes in the `<video>` element.
-Video-to-load-

-Source- tells the browser where the video file is located using web address or file location   ____

-Controls-we can add the controls attribute without having to install additional plug ins. tells the browser to play pause or full screen options.
The video control should be there.

3. Why is it important to have **fallback content** inside the `<video>` element? *incase the video fails to load.* Not all all browsers support video format. MP$ are the most versatile. *It is important to have fallback content inside the <video> element because not all browsers or devices support the video format or the <video> tag. Fallback content provides an alternative, such as a message or a download link, so users can still access the information even if the video cannot play. This helps make the webpage more accessible and user-friendly.*

4. Write a very short story where `<audio>` and `<video>` are characters.

In a small digital village lived two friends named <audio> and <video>. <audio> loved to share music, voices, and sounds that made people listen closely. <video> enjoyed showing colorful pictures and moving scenes that told exciting stories.

One day the webpage was quiet, so <audio> began playing a cheerful tune while <video> showed a bright animation. Together they brought the page to life. The visitors realized that while each was special on their own, <audio> and <video> worked best when they shared their talents.

[A Complete Guide To Grid](https://css-tricks.com/snippets/css/complete-guide-grid/){:target="_blank"}

How does Grid layout differ from Flex?
CSS Grid and Flexbox are both layout systems, but they are designed for different types of layouts.

Grid is a two-dimensional layout system, meaning it controls both rows and columns at the same time. It is useful for creating full page layouts or complex structures.

Flexbox is a one-dimensional layout system, meaning it works in one direction at a time—either a row or a column. It is best for aligning items in a single line or small components like menus or buttons.

Grid: controls rows and columns (2D layout)

Flexbox: controls one direction (row or column) at a time (1D layout).

 Grid container, grid item, and grid line are a few important terms to understand when using Grid. Please describe these terms in a few sentences. *Grid container Parent element is where you display the grid containing the structure, **grid item**- are the direct child that's positioned inside the container. 

 [Responsive Images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images){:target="_blank"}

1. Besides making a site visually appealing across different screen sizes, why should developers make images responsive?
Developers should make images **responsive** not only for appearance on different screen sizes but also to improve performance and user experience. Responsive images allow the browser to load the correct image size for a device, which reduces file size and speeds up page loading. This helps users on slower connections or mobile devices use the site more easily and also saves bandwidth.  reduces data useage , smaller images are better for SEO, faster sites are better for seo.
stretched images are an issue. Accessibility should be on all websites. All images should look good and be avail on all devices. **Responsive** images allow the browser to load the correct image size for a device, which reduces file size and speeds up page loading.

2. Define the following `<img>` attributes `srcset` and `sizes`. Write an example of how they are used. 
srcset

The srcset attribute provides a list of different image files and their widths. This allows the browser to choose the most appropriate image to load depending on the user’s screen size or resolution.

sizes

The sizes attribute tells the browser how much space the image will take up on the screen in different situations. This helps the browser decide which image from the srcset list should be loaded.

If you are creating an icon or logo, you may need multiple image sizes for different screen sizes and devices.

You can manually adjust the image size or use the srcset attribute to let the browser choose the best image automatically.

The srcset attribute provides a list of image files with different resolutions or widths.

The browser will then select the image that fits best in the available space on the webpage.

srcset works like an array (a list of options) where multiple image versions are provided.

3. How is `srcset` more helpful for responsive images than CSS or JavaScript?
srcset is more helpful for responsive images because it allows the browser to choose the most appropriate image size automatically based on the user’s screen size, resolution, and device capabilities. This means the browser only downloads the image it actually needs, which improves loading speed and saves bandwidth.

Using CSS or JavaScript can change how an image is displayed, but the browser may still download the full-size image, even if it is shown smaller on the page. With srcset, the browser can select and load a smaller or larger image file before downloading, making it more efficient for responsive design.

## Notes

1. What is Object-Oriented Programming?

1. To use CSS Grid, the parent element (container) must have the `display` property set to what value?

1. The Array method of `__push()_____` adds one or more elements to the end of an array.

1. The Array method of `___pop()____` removes the **last** element from an array.

1. The Array method of `_shift()______` removes the **first** element from an array.

1. The Array method of `_unshift()______` adds one or more elements to the beginning of an array.

1. The Array method of `_splice()______` changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.

example array js
const numbers = [1, 2, 3, 4, 5]; (1 arrays, 4 elements) becvause 1 would repreent zero.
