117-132 154-154

1) - [x] Transmitting Data Via the Client
    - passing data via the client to get the same data in the subsecuent request maybe on the same server or the other server in the step by step process

    1) Hidden Form Fields
        - when you can modify the hidden price field check for entering negative price which will credit balance in your account
    2) HTTP Cookies
        - modify the cookie when the cookie received from the server is attached in the subsequent request
    3) URL Parameters
        - modify the URL parameters
    4) The Referer Header
        - used to track from where the request originated. So fake it to be originated from where it accepts the entry
    5) Opaque Data
    6) The ASP.NET ViewState
        - ViewState for sending Opaque data
        - check for MAC protection enabled or disabled
        - Burp automatically reports any pages that use the ViewState without MAX protection enabled
2) - [x] Capturing User Data: HTML Forms
    1) Length Limits
        - change the maxLength value in the form element
        - if server validation is absent then it can exploit other vulnerabilities like SQL Injection, XSS, or buffer overflows
    2) Script-Based Validation
        - make the validation be manipulate when receiving the response from the server
    3) Disabled Elements
        - check the disabled element make difference in the server-side processing
        - use html modification feature of burp suite
3) - [] Capturing User Data: Browser Extensions
    1) Common Browser Extension Technologies
    2) Approaches to Browser Extensions
    3) Intercepting Traffic from Browser Extensions
    4) Decompiling Browser Extensions
    5) Native Client Components
    6) Attaching a Debugger
    7) Native Client Components
4) - [x] Handling Client-Side Data Securely
    1) Transmitting Data Via the Client
        - when sending a encrypted data to the user, encrypted data should include some extra information with the data that cannot be replaced or tempered.
        - ViewState of ASP.NET should activate MAC
    2) Validating Client-Generated Data
        - circumventing client side validation is not valid report, if the validation is lagged in server side then it can be a valid report
        - but at least the validation should be available in server side
        - check for JS disable and cookies disable
    3) Logging and Alerting
        - Alert the system or team as soon as any possible malicious payload

Q) how to bypass the counting of failed attempt stored in cookies