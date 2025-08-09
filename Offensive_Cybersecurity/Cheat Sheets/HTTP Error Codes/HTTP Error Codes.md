#HTTPErrorCodes #WEB

| Code    | Name                       | Meaning                                                                        | Next Step in Pentest                                                                        |
| ------- | -------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------- |
| **400** | Bad Request                | Server couldn't understand the request (malformed syntax, invalid parameters). | Check request format, try fuzzing params, inspect special characters and encoding.          |
| **401** | Unauthorized               | Auth required and not provided or invalid.                                     | Enumerate auth type, try default creds, brute-force, token replay, credential stuffing.     |
| **403** | Forbidden                  | Auth provided (or not needed) but permission denied.                           | Attempt ACL bypass, change HTTP method, use path obfuscation (`/admin/.`, `%2e`), spoof IP. |
| **404** | Not Found                  | Resource not found or intentionally hidden.                                    | Fuzz directories/files, use wordlists (dirb/ffuf), try case changes or extensions.          |
| **405** | Method Not Allowed         | HTTP method not supported for this resource.                                   | Try alternative methods (`POST`, `PUT`, `DELETE`, `OPTIONS`) for hidden functionality.      |
| **406** | Not Acceptable             | Resource can't return content matching `Accept` headers.                       | Modify `Accept` headers, attempt content negotiation fuzzing.                               |
| **407** | Proxy Authentication Req   | Proxy server demands authentication before forwarding the request.             | Try proxy auth brute-force, bypass proxy if possible, check for open internal paths.        |
| **408** | Request Timeout            | Server timed out waiting for request.                                          | Adjust payload size, slow down requests (possible WAF), use keep-alive or retry.            |
| **409** | Conflict                   | Request conflicts with current server state.                                   | Investigate API logic, try race conditions, change request ordering.                        |
| **410** | Gone                       | Resource used to exist but is permanently removed.                             | Check archive services (Wayback Machine), look for renamed/moved endpoints.                 |
| **411** | Length Required            | Server requires `Content-Length` header.                                       | Add proper `Content-Length` header, test for request smuggling.                             |
| **413** | Payload Too Large          | Request entity larger than server is willing to process.                       | Reduce payload, try chunked encoding, test for upload bypass.                               |
| **414** | URI Too Long               | URL exceeds maximum length.                                                    | Shorten parameters, try moving data to body instead of query string.                        |
| **415** | Unsupported Media Type     | Server refuses request due to unsupported format.                              | Change `Content-Type`, try polyglot payloads, bypass upload restrictions.                   |
| **429** | Too Many Requests          | Rate limiting triggered.                                                       | Slow down, rotate IPs, use rate-limit bypass (X-Forwarded-For spoof, parallel sessions).    |
| **500** | Internal Server Error      | Generic server crash or unhandled condition.                                   | Send malformed inputs, fuzz parameters, check error messages for tech stack info.           |
| **501** | Not Implemented            | Server doesn't support the request method.                                     | Try standard methods, check if request is hitting intended endpoint.                        |
| **502** | Bad Gateway                | Invalid response from upstream server.                                         | Look for SSRF possibilities, check internal services.                                       |
| **503** | Service Unavailable        | Server temporarily overloaded or under maintenance.                            | Retry later, check if functionality is intentionally disabled, test caching layers.         |
| **504** | Gateway Timeout            | Upstream server failed to respond in time.                                     | Test for SSRF timeouts, adjust timeout-based payloads, slow-loris style attacks.            |
| **505** | HTTP Version Not Supported | Server refuses requested HTTP version.                                         | Downgrade/upgrade HTTP version, test for protocol downgrade vulnerabilities.                |
