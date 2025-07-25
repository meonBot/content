---
title: Last-Modified header
short-title: Last-Modified
slug: Web/HTTP/Reference/Headers/Last-Modified
page-type: http-header
browser-compat: http.headers.Last-Modified
sidebar: http
---

The HTTP **`Last-Modified`** {{glossary("response header")}} contains a date and time when the origin server believes the resource was last modified.
It is used as a validator in [conditional requests](/en-US/docs/Web/HTTP/Guides/Conditional_requests) ({{HTTPHeader("If-Modified-Since")}} or {{HTTPHeader("If-Unmodified-Since")}}) to determine if a requested resource is the same as one already stored by the client.
It is less accurate than an {{HTTPHeader("ETag")}} for determining file contents, but can be used as a fallback mechanism if ETags are unavailable.

`Last-Modified` is also used by [crawlers](/en-US/docs/Glossary/Crawler) to adjust crawl frequency, by browsers in [heuristic caching](/en-US/docs/Web/HTTP/Guides/Caching#heuristic_caching), and by content management systems (CMS) to display the time the content was last modified.

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">Header type</th>
      <td>{{glossary("Response header")}}, {{Glossary("Representation header")}}</td>
    </tr>
    <tr>
      <th scope="row">{{Glossary("Forbidden request header")}}</th>
      <td>No</td>
    </tr>
    <tr>
      <th scope="row">
        {{Glossary("CORS-safelisted response header")}}
      </th>
      <td>Yes</td>
    </tr>
  </tbody>
</table>

## Syntax

```http
Last-Modified: <day-name>, <day> <month> <year> <hour>:<minute>:<second> GMT
```

## Directives

- `<day-name>`
  - : One of "Mon", "Tue", "Wed", "Thu", "Fri", "Sat", or "Sun" (case-sensitive).
- `<day>`
  - : 2 digit day number, e.g., "04" or "23".
- `<month>`
  - : One of "Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec" (case-sensitive).
- `<year>`
  - : 4 digit year number, e.g., "1990" or "2016".
- `<hour>`
  - : 2 digit hour number, e.g., "09" or "23".
- `<minute>`
  - : 2 digit minute number, e.g., "04" or "59".
- `<second>`
  - : 2 digit second number, e.g., "04" or "59".
- GMT
  - : Greenwich Mean Time. HTTP dates are always expressed in GMT, never in local time.

## Examples

```http
Last-Modified: Wed, 21 Oct 2015 07:28:00 GMT
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{HTTPHeader("Etag")}}
- [HTTP Conditional Requests](/en-US/docs/Web/HTTP/Guides/Conditional_requests) guide
- {{HTTPHeader("If-Match")}}, {{HTTPHeader("If-Modified-Since")}}, {{HTTPHeader("If-Unmodified-Since")}}, {{HTTPHeader("If-None-Match")}} conditional request headers
- {{HTTPStatus("304", "304 Not Modified")}}, {{HTTPStatus("412", "412 Precondition Failed")}} response status codes
