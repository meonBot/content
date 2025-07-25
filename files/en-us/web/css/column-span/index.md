---
title: column-span
slug: Web/CSS/column-span
page-type: css-property
browser-compat: css.properties.column-span
sidebar: cssref
---

The **`column-span`** [CSS](/en-US/docs/Web/CSS) property makes it possible for an element to span across all columns when its value is set to `all`.

{{InteractiveExample("CSS Demo: column-span")}}

```css interactive-example-choice
column-span: none;
```

```css interactive-example-choice
column-span: all;
```

```html interactive-example
<section id="default-example">
  <div class="multicol-element">
    <p>
      London. Michaelmas term lately over, and the Lord Chancellor sitting in
      Lincoln's Inn Hall.
    </p>
    <div id="example-element">Spanner?</div>
    <p>
      Implacable November weather. As much mud in the streets as if the waters
      had but newly retired from the face of the earth, and it would not be
      wonderful to meet a Megalosaurus, forty feet long or so, waddling like an
      elephantine lizard up Holborn Hill.
    </p>
  </div>
</section>
```

```css interactive-example
.multicol-element {
  width: 100%;
  text-align: left;
  column-count: 3;
}

.multicol-element p {
  margin: 0;
}

#example-element {
  background-color: rebeccapurple;
  padding: 10px;
  color: #fff;
}
```

An element that spans more than one column is called a **spanning element**.

## Syntax

```css
/* Keyword values */
column-span: none;
column-span: all;

/* Global values */
column-span: inherit;
column-span: initial;
column-span: revert;
column-span: revert-layer;
column-span: unset;
```

The `column-span` property is specified as one of the keyword values listed below.

### Values

- `none`
  - : The element does not span multiple columns.
- `all`
  - : The element spans across all columns. Content in the normal flow that appears before the element is automatically balanced across all columns before the element appears. The element establishes a new block formatting context.

## Formal definition

{{cssinfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Making a heading span columns

In this example, the heading is made to span across all the columns of the article.

#### HTML

```html
<article>
  <h2>Header spanning all of the columns</h2>
  <p>
    The h2 should span all the columns. The rest of the text should be
    distributed among the columns.
  </p>
  <p>
    This is a bunch of text split into three columns using the CSS `columns`
    property. The text is equally distributed over the columns.
  </p>
  <p>
    This is a bunch of text split into three columns using the CSS `columns`
    property. The text is equally distributed over the columns.
  </p>
  <p>
    This is a bunch of text split into three columns using the CSS `columns`
    property. The text is equally distributed over the columns.
  </p>
  <p>
    This is a bunch of text split into three columns using the CSS `columns`
    property. The text is equally distributed over the columns.
  </p>
</article>
```

#### CSS

```css
article {
  columns: 3;
}

h2 {
  column-span: all;
}
```

#### Result

{{EmbedLiveSample('Making_a_heading_span_columns', 'auto', 260)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Spanning and balancing columns](/en-US/docs/Web/CSS/CSS_multicol_layout/Spanning_balancing_columns)
- [Inline-level elements](/en-US/docs/Glossary/Inline-level_content)
- {{domxref("HTMLSpanElement")}}
