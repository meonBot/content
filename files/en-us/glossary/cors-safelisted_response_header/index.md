---
title: CORS-safelisted response header
slug: Glossary/CORS-safelisted_response_header
page-type: glossary-definition
sidebar: glossarysidebar
---

A **CORS-safelisted response header** (also known as "simple response header") is an [HTTP header](/en-US/docs/Web/HTTP/Reference/Headers) in a [CORS](/en-US/docs/Web/HTTP/Guides/CORS) response that it is considered _safe_ to expose to client scripts. Only safelisted response headers are made available to web pages.

By default, the safelist includes the following response headers:

- {{HTTPHeader("Cache-Control")}}
- {{HTTPHeader("Content-Language")}}
- {{HTTPHeader("Content-Length")}}
- {{HTTPHeader("Content-Type")}}
- {{HTTPHeader("Expires")}}
- {{HTTPHeader("Last-Modified")}}
- {{HTTPHeader("Pragma")}}

Additional headers can be added to the safelist using {{HTTPHeader("Access-Control-Expose-Headers")}}.

## Examples

### Extending the safelist

You can extend the list of CORS-safelisted response headers by using the {{HTTPHeader("Access-Control-Expose-Headers")}} header:

```http
Access-Control-Expose-Headers: X-Custom-Header, Content-Encoding
```

## See also

- [HTTP](/en-US/docs/Web/HTTP)
- [HTTP headers](/en-US/docs/Web/HTTP/Reference/Headers)
- {{HTTPHeader("Access-Control-Expose-Headers")}}
- Related glossary terms:
  - {{Glossary("CORS")}}
  - {{Glossary("CORS-safelisted_request_header", "CORS-safelisted request header")}}
  - {{Glossary("Forbidden request header")}}
  - {{Glossary("Request header")}}
