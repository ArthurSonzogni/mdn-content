---
title: HTMLIFrameElement.credentialless
slug: Web/API/HTMLIFrameElement/credentialless
page-type: web-api-instance-property
tags:
  - API
  - credentialless
  - HTML DOM
  - HTMLIFrameElement
  - Property
  - Reference
  - Experimental
browser-compat: api.HTMLIFrameElement.credentialless
---

{{APIRef("HTML DOM")}}{{SeeCompatTable}}

The **`credentialless`** property of the {{domxref("HTMLIFrameElement")}} interface indicates whether the {{htmlelement("iframe")}} is credentialless, meaning that its content is loaded in a new, ephemeral context.

This context does not have access to the parent context's shared storage and credentials. In return, the {{httpheader("Cross-Origin-Embedder-Policy")}} (COEP) embedding rules can be lifted, so documents with COEP set can embed third-party documents that do not. See [IFrame credentialless](/en-US/docs/Web/Security/IFrame_credentialless) for a deeper explanation.

## Value

A boolean. The default value is `false`; set it to `true` to make the `<iframe>` credentialless.

## Examples

### Get

Specify a credentialless `<iframe>` like so:

```html
<iframe src="https://en.wikipedia.org/wiki/Spectre_(security_vulnerability)"
        title="Spectre vulnerability Wikipedia page"
        width="960"
        height="600"
        credentialless>
```

Return the `credentialless`  property value:

```js
const iframeElem = document.querySelector('iframe');
console.log(iframeElem.credentialless); // will return true in supporting browsers
```

### Set

Alternatively, specify the minimum of details in the HTML:

```html
<iframe width="960"
        height="600">
</iframe>
```

And set `credentialless` to `true` then load the `<iframe>` contents via script:

```js
const iframeElem = document.querySelector('iframe');

iframeElem.credentialless = true;
iframeElem.title = 'Spectre vulnerability Wikipedia page';
iframeElem.src = 'https://en.wikipedia.org/wiki/Spectre_(security_vulnerability)';
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [IFrame credentialless](/en-US/docs/Web/Security/IFrame_credentialless)
- {{htmlelement("iframe")}}
