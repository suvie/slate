# Errors

The Cognism API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Issues with the request
401 | Unauthorized -- Access Token or Security Key wrong
403 | Forbidden -- Request not available for the account
404 | Not Found -- URL could not be found
405 | Method Not Allowed -- Method invalid
406 | Not Acceptable -- Request format wrong - check your JSON
410 | Gone -- Requested API has been removed from server
429 | Too Many Requests -- Too many requests at once
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.
