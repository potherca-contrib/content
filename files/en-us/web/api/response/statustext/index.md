---
title: Response.statusText
slug: Web/API/Response/statusText
tags:
  - API
  - Experimental
  - Fetch
  - Property
  - Reference
  - Response
  - statusText
browser-compat: api.Response.statusText
---
{{APIRef("Fetch")}}

The **`statusText`** read-only property of the
{{domxref("Response")}} interface contains the status message corresponding to the
status code (e.g., `OK` for `200`).

## Syntax

```js
var myStatusText = response.statusText;
```

### Value

A {{jsxref("String")}}.

The default value is "". Note that HTTP/2 [does not
support](https://fetch.spec.whatwg.org/#concept-response-status-message) status messages.

## Example

In our [Fetch
Response example](https://github.com/mdn/fetch-examples/tree/gh-pages/fetch-response) (see [Fetch Response
live](https://mdn.github.io/fetch-examples/fetch-response/)) we create a new {{domxref("Request")}} object using the
{{domxref("Request.Request","Request()")}} constructor, passing it a JPG path. We then
fetch this request using {{domxref("fetch()")}}, extract a blob
from the response using {{domxref("Response.blob")}}, create an object URL out of it using
{{domxref("URL.createObjectURL")}}, and display this in an {{htmlelement("img")}}.

Note that at the top of the `fetch()` block we log the response
`statusText` value to the console.

```js
var myImage = document.querySelector('img');

var myRequest = new Request('flowers.jpg');

fetch(myRequest).then(function(response) {
  console.log(response.statusText); // returns "OK" if the response returned successfully
  response.blob().then(function(myBlob) {
    var objectURL = URL.createObjectURL(myBlob);
    myImage.src = objectURL;
  });
});
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [ServiceWorker API](/en-US/docs/Web/API/Service_Worker_API)
- [HTTP access control (CORS)](/en-US/docs/Web/HTTP/CORS)
- [HTTP](/en-US/docs/Web/HTTP)
