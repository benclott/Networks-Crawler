## Overview

Upon execution, the web crawler initiates by establishing a connection to the Fakebook server using the provided server address and port. The crawler begins its exploration from the root path /fakebook/, systematically traversing through the website's paths. It sends HTTP GET requests to each path and awaits the server's response.

As the crawler receives responses from the server, it parses the HTML content to identify new links and extract any secret flags embedded within the HTML. If the response contains a login form, the crawler automatically submits the provided credentials to access restricted areas of the website.

Throughout the crawling process, the script handles various HTTP response codes, including 200 (OK), 302 (Redirect), and client errors (e.g., 404). Robust error handling mechanisms ensure graceful management of errors, maintaining stability and continuity in the crawling process.

To maintain persistent interaction with the server, the crawler utilizes session cookies and CSRF tokens for authentication. These tokens are extracted from the server's response headers and included in subsequent requests.

As the crawler continues to explore the website, it maintains a count of the pages searched. Every 100 pages searched, the crawler prints a progress update, indicating the number of pages searched.

The implementation of the web crawler prioritizes efficiency and reliability, ensuring that it effectively gathers information while maintaining stability throughout the crawling process. Python's standard libraries, including socket, ssl, html.parser, urllib.parse, and gzip, are utilized to handle various aspects of communication, parsing, and error management.

Overall, the execution of the program involves a systematic exploration of the Fakebook website, with the crawler navigating through paths, extracting information, and handling interactions with the server to fulfill its crawling objectives.