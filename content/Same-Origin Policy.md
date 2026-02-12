Security mechanism in browsers restricting how a document or script loaded by one origin can interact with resources from another origin. It prevents JS from accessing [[HTTP]] request responses.

For example, it prevents a malicious website from running JS in a browser to read data from company intranet.

Origins are determined by the `Origin` header and are defined by
- a protocol (`https://`, `ftp://`)
- a port if specified (`:8080`)
- a host (domain name or IP address)

Enabled by default in most browsers, websites can enforce exceptions with CORS headers
- `Access-Control-Allow-Origin` 
- `Access-Control-Allow-Methods`
- `Access-Control-Allow-Headers`
- `Access-Control-Allow-Credentials`

`document.domain` can allow two subdomains to loosen SOP if they have the same protocol and a common domain suffix (doesn't work with TLDs) by specifying the same domain.

iframes can't access the DOM of a website with a different origin. Adding the `sandbox` attribute gives an extra layer of security: it disables JS, access to parent, forms, and puts opaque origins by default.

Opaque origins (`data`, `blob`) are considered equal to no other origin (always cross-origin).