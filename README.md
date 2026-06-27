 # web-request--flow
demonstrating the web request flow, including DNS lookup, browser network analysis, and HTTP request/response inspection.
Introduction
When we type a website URL (for example, https://shorterloop.com) into the browser and press Enter, the webpage does not appear instantly. Behind the scenes, several networking steps occur within milliseconds before the browser displays the page.
1. DNS (Domain Name System)
What it does: DNS converts the website name into an IP address.
Example:

shorterloop.com
        ↓
76.76.21.21
The browser cannot communicate using the website name, so it first asks a DNS server for the corresponding IP address.
Command used:
Bash
nslookup shorterloop.com
If available:
Bash
dig shorterloop.com +short

2. TCP (Transmission Control Protocol)
Once the IP address is known, the browser establishes a TCP connection with the server.
This happens using the Three-Way Handshake:
Client → SYN
Server → SYN-ACK
Client → ACK
This ensures a reliable connection before any data is exchanged.

4. TLS (Transport Layer Security)
Since the website uses HTTPS, a TLS handshake occurs.
During this step:
The server sends its SSL/TLS certificate.
The browser verifies the certificate.
Both create encryption keys.
Now all communication is encrypted and secure.

6. HTTP Request
The browser sends an HTTP request to the server.
Example:

GET /
The server processes the request and prepares the webpage.

5. HTTP Response
The server sends back:
HTML
CSS
JavaScript
Images
Fonts
Status Code (e.g., 200 OK)
The browser may send many additional requests to download all these files.
