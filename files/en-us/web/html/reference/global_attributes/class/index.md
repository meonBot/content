---
title: HTML class global attribute
short-title: class
slug: Web/HTML/Reference/Global_attributes/class
page-type: html-attribute
browser-compat: html.global_attributes.class
sidebar: htmlsidebar
---

The **`class`** [global attribute](/en-US/docs/Web/HTML/Reference/Global_attributes) is a list of the classes of the element, separated by [ASCII whitespace](/en-US/docs/Glossary/Whitespace#in_html).

{{InteractiveExample("HTML Demo: class", "tabbed-standard")}}

```html interactive-example
<p>Narrator: This is the beginning of the play.</p>

<p class="note editorial">Above point sounds a bit obvious. Remove/rewrite?</p>

<p>Narrator: I must warn you now folks that this beginning is very exciting.</p>

<p class="note">[Lights go up and wind blows; Caspian enters stage right]</p>
```

```css interactive-example
.note {
  font-style: italic;
  font-weight: bold;
}

.editorial {
  background: rgb(255 0 0 / 0.25);
  padding: 10px;
}

.editorial::before {
  content: "Editor: ";
}
```

## Syntax

The `class` attribute is a list of class values separated by [ASCII whitespace](/en-US/docs/Glossary/Whitespace#in_html).

Each class value may contain any Unicode characters (except, of course, ASCII whitespace). However, when used in CSS selectors, either from JavaScript using APIs like {{domxref("Document.querySelector()")}} or in CSS stylesheets, class attribute values must be valid [CSS identifiers](/en-US/docs/Web/CSS/ident). This means that if a class attribute value is not a valid CSS identifier (for example, `my?class` or `1234`) then it must be escaped before being used in a selector, either using the {{domxref("CSS.escape_static", "CSS.escape()")}} method or [manually](/en-US/docs/Web/CSS/ident#escaping_characters).

For this reason, it's recommended that developers choose values for class attributes that are valid CSS identifiers that don't require escaping.

## Description

Classes allow CSS and JavaScript to select and access specific elements via the [class selectors](/en-US/docs/Web/CSS/Class_selectors) or functions like the {{domxref("document.getElementsByClassName()")}}.

Though the specification doesn't put requirements on the name of classes, web developers are encouraged to use names that describe the semantic purpose of the element, rather than the presentation of the element. For example, _attribute_ to describe an attribute rather than _italics_, although an element of this class may be presented by _italics_. Semantic names remain logical even if the presentation of the page changes.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- All [global attributes](/en-US/docs/Web/HTML/Reference/Global_attributes).
- {{domxref('element.className')}}
- {{domxref('element.classList')}}
- [Introduction to CSS](/en-US/docs/Learn_web_development/Core/Styling_basics)
