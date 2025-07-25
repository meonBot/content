---
title: Implementing image sprites in CSS
short-title: Implementing image sprites
slug: Web/CSS/CSS_images/Implementing_image_sprites_in_CSS
page-type: guide
sidebar: cssref
---

**Image sprites** are used in numerous web apps where multiple images are used. Rather than include each image as a separate image file, it is much more memory- and bandwidth-friendly to send them as a single image; using background position as a way to distinguish between individual images in the same image file, so the number of HTTP requests is reduced.

> [!NOTE]
> When using HTTP/2, it may in fact be more bandwidth-friendly to use multiple small requests.

## Implementation

Suppose an image is given to every item with class `tool-btn`:

```css
.tool-btn {
  background: url(myfile.png);
  display: inline-block;
  height: 20px;
  width: 20px;
}
```

A background position can be added either as two x, y values after the {{cssxref("url_value", "&lt;url&gt;")}} in the background, or as {{cssxref("background-position")}}. For example:

```css
#btn1 {
  background-position: -20px 0px;
}

#btn2 {
  background-position: -40px 0px;
}
```

This would slide the starting point of the background image for the element with the ID `btn1` 20 pixels to the left and the element with the ID `btn2` 40 pixels to the left (assuming they have the class `tool-btn` assigned and are affected by the image rule above).

Similarly, you can also make hover states by targeting `#btn:hover`.

## See also

- [Full working demo at CSS Tricks](https://css-tricks.com/snippets/css/perfect-css-sprite-sliding-doors-button/)
