---
title: "InputEvent: dataTransfer property"
short-title: dataTransfer
slug: Web/API/InputEvent/dataTransfer
page-type: web-api-instance-property
browser-compat: api.InputEvent.dataTransfer
---

{{APIRef("UI Events")}}

The **`dataTransfer`** read-only property of the
{{domxref("InputEvent")}} interface returns a {{domxref("DataTransfer")}} object
containing information about richtext or plaintext data being added to or removed from
editable content.

## Value

A {{domxref("DataTransfer")}} object or `null`. The spec has an [overview](https://w3c.github.io/input-events/#overview) of its value in various cases.

## Examples

In the following simple example we've set up an event listener on the [input](/en-US/docs/Web/API/Element/input_event) event so that when any
content is pasted into the contenteditable {{htmlelement("p")}} element, its HTML source
is retrieved via the
[`InputEvent.dataTransfer.getData()`](/en-US/docs/Web/API/DataTransfer/getData)
method and reported in the paragraph below the input.

Try copying and pasting some of the content provided to see the effects.

```html
<p><span style="font-weight: bold; color: blue">Whoa, bold blue text!</span></p>
<p>
  <span style="font-style: italic; color: red">Exciting: italic red text!</span>
</p>
<p>Boring normal text ;-(</p>

<hr />

<p contenteditable="true">
  Go on, try pasting some content into this editable paragraph and see what
  happens!
</p>

<p class="result"></p>
```

```js
const editable = document.querySelector("p[contenteditable]");
const result = document.querySelector(".result");

editable.addEventListener("input", (e) => {
  result.textContent = e.dataTransfer.getData("text/html");
});
```

{{EmbedLiveSample('Examples', '100%', 250)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
