---
title: ::backdrop
slug: Web/CSS/::backdrop
page-type: css-pseudo-element
browser-compat: css.selectors.backdrop
sidebar: cssref
---

The **`::backdrop`** [CSS](/en-US/docs/Web/CSS) [pseudo-element](/en-US/docs/Web/CSS/Pseudo-elements) is a box the size of the {{Glossary("viewport")}}, which is rendered immediately beneath any element being presented in the {{glossary("top layer")}}.

{{InteractiveExample("CSS Demo: ::backdrop", "tabbed-shorter")}}

```css interactive-example
button {
  font-size: 1.2rem;
  padding: 5px 15px;
}

dialog::backdrop {
  background-color: salmon;
}
```

```html interactive-example
<button id="showDialogBtn">Show a dialog</button>

<dialog id="favDialog">
  <form method="dialog">
    <p>The background shown outside of this dialog is a backdrop.</p>
    <button id="confirmBtn">Close the dialog</button>
  </form>
</dialog>
```

```js interactive-example
const showDialogBtn = document.getElementById("showDialogBtn");
const favDialog = document.getElementById("favDialog");

showDialogBtn.addEventListener("click", () => favDialog.showModal());
```

## Syntax

```css
::backdrop {
  /* ... */
}
```

## Description

Backdrops appear in the following instances:

- Elements which have been placed in fullscreen mode using the [Fullscreen API](/en-US/docs/Web/API/Fullscreen_API) {{domxref("Element.requestFullscreen()")}} method.
- {{HTMLElement("dialog")}} elements that have been shown in the top layer via a {{domxref("HTMLDialogElement.showModal()")}} call.
- {{domxref("Popover API", "Popover", "", "nocode")}} elements that have been shown in the top layer via a {{domxref("HTMLElement.showPopover()")}} call.

When multiple elements have been placed into the top layer, each one has its own `::backdrop` pseudo-element.

```css
/* Backdrop is only displayed when dialog is opened with dialog.showModal() */
dialog::backdrop {
  background: rgb(255 0 0 / 25%);
}
```

Elements are placed in a last-in/first out (LIFO) stack in the top layer. The `::backdrop` pseudo-element makes it possible to obscure, style, or completely hide everything located below a top layer element.

`::backdrop` neither inherits from nor is inherited by any other elements. No restrictions are made on what properties apply to this pseudo-element.

## Examples

### Styling a modal dialog's backdrop

In this example, we use the `::backdrop` pseudo-element to style the backdrop that is used when a modal {{htmlelement("dialog")}} is open.

#### HTML

We include a {{htmlelement("button")}} that, when clicked, will open the included `<dialog>`. When the `<dialog>` is opened, we give focus to the button that closes the dialog:

```html
<dialog>
  <button autofocus>Close</button>
  <p>This modal dialog has a beautiful backdrop!</p>
</dialog>
<button>Show the dialog</button>
```

#### CSS

We add a background to the backdrop, creating a colorful donut using [CSS gradients](/en-US/docs/Web/CSS/gradient):

```css
::backdrop {
  background-image:
    radial-gradient(
      circle,
      #fff 0 5vw,
      transparent 5vw 20vw,
      #fff 20vw 22.5vw,
      #eee 22.5vw
    ),
    conic-gradient(
      #272b66 0 50grad,
      #2d559f 50grad 100grad,
      #9ac147 100grad 150grad,
      #639b47 150grad 200grad,
      #e1e23b 200grad 250grad,
      #f7941e 250grad 300grad,
      #662a6c 300grad 350grad,
      #9a1d34 350grad 400grad,
      #43a1cd 100grad 150grad,
      #ba3e2e
    );
}
```

#### JavaScript

The dialog is opened modally using the [`.showModal()`](/en-US/docs/Web/API/HTMLDialogElement/showModal) method and closed using the [`.close()`](/en-US/docs/Web/API/HTMLDialogElement/close) method.

```js
const dialog = document.querySelector("dialog");
const showButton = document.querySelector("dialog + button");
const closeButton = document.querySelector("dialog button");

// "Show the dialog" button opens the dialog modally
showButton.addEventListener("click", () => {
  dialog.showModal();
});

// "Close" button closes the dialog
closeButton.addEventListener("click", () => {
  dialog.close();
});
```

#### Results

{{EmbedLiveSample("Styling a modal dialog's backdrop", 450, 300)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{cssxref(":fullscreen")}} pseudo-class
- {{HTMLElement("dialog")}} HTML element
- [Fullscreen API](/en-US/docs/Web/API/Fullscreen_API)
- [`popover`](/en-US/docs/Web/HTML/Reference/Global_attributes/popover) HTML global attribute
- [Popover API](/en-US/docs/Web/API/Popover_API)
