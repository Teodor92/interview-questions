# Web Interview Questions

## 1. What is AJAX? How does it work?

AJAX(Asynchronous Javascript And XML) uses a combination of technologies to load content on the web-page dynamically  without a full reload:
- HTML and CSS for marking up and styling information.
- The DOM accessed with JavaScript to dynamically display and interact with the information presented.
- A method for exchanging data asynchronously between browser and server, thereby avoiding page reloads. The XMLHttpRequest (XHR) object is usually used, but sometimes an IFrame object or a dynamically added tag is used instead.
- A format for the data sent to the browser. Common formats include XML, pre-formatted HTML, plain text, and JavaScript Object Notation (JSON). This data could be created dynamically by some form of server-side scripting.

## 2. What is CORS? How does it work? What is preflight?

Cross-Origin Resource Sharing (CORS) is a web browser security feature that controls how web applications at one origin can interact with resources at a different origin. It is an integral part of the browser's security model, enforcing the same-origin policy which restricts documents or scripts from different origins from accessing each other's resources.

### How Does CORS Work?

CORS involves a set of steps and checks performed by both the browser and the server:

1. **Browser's Check**: When a page requests a resource from a different origin, the browser first checks the CORS policy of that resource.
2. **Server's Response**: The server hosting the resource responds with specific CORS headers, such as `Access-Control-Allow-Origin`, indicating whether the resource is accessible.
3. **Conditional Access**: If the server's CORS policy allows the request, the browser proceeds with loading the resource. Otherwise, the request is blocked.

### What is Preflight in CORS?

Preflight is a CORS process used for validating certain types of cross-origin requests before the actual request is made:

- **Definition**: Preflight is an additional step in CORS that is used for certain types of cross-origin requests.
- **Purpose**: Preflight requests are sent to the server to determine if the actual request is safe to send. It's like asking for permission or a "green light" before the actual request.
- **Trigger**: Preflight requests are typically triggered by HTTP requests that use methods other than GET, HEAD, or POST, or that use POST with certain MIME types, or that include custom headers.
- **Process**: The preflight request is an HTTP OPTIONS request sent to the server hosting the other-origin resource. This request includes headers like Access-Control-Request-Method and Access-Control-Request-Headers that inform the server about the method and headers of the actual request.
- **Server Response**: If the server responds to the preflight request with appropriate CORS headers that approve the request's method and headers, the browser proceeds to send the actual request.

## 3. What are cookies? How does it work?

Best answer ever! - [https://stackoverflow.com/a/48654382/2109394](https://stackoverflow.com/a/48654382/2109394)

## 4. Which are the 5 groups of HTTP codes? What do we use them for?

- Informational responses (100 – 199)
- Successful responses (200 – 299)
- Redirects (300 – 399)
- Client errors (400 – 499)
- Server errors (500 – 599)
