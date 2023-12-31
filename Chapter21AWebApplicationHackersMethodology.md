A Web Application Hacker's Methodology
791 - 798
1) - [x] Map the Application's Content
    1.1) Explore Visible Content
        - Manually go through each link submit every form and then spider the website
    1.2) Consult Public Resources
    1.3) Discover Hidden Content
        - How application handles non-existent items
        - Understand name convertion of pages
        - Use Automation techniques
    1.4) Discover Default Content
        - Run Nikto -> to detech default or well-known Content
        - Request the server's root directory
    1.5) Enumerate Identifier-Specified Functions
        - Identify functions like /admin.jsp?action=editUser or /main.php?func=A21
    1.6) Test for Debug Parameter
2) - [x] Analyze the Application
    2.1) Identify Functionality
        - the core functionality
        - the core security mechanism like authentication, session management, access control and functions that support them like user registration and account recovery
        - redirects, off-site links, error messages, admin and loging functions
        - any functionality that diverges from normal GUI -> single it out for in depth testing
    2.2) Identify Data Entry Points
        - identify the places where user input are use for application's processingm including URLs, quer string parameters, POST data, cookies, etc
    2.3) Identify the Technologies Understand
        - check Server header
        - run httprint to fingerprint the web server
        - review file extensionsm session tokens and cookies names
    2.4) Map the Attack Surface
        - map the things that are visible from a normal client eg: a function to retrieve customer orders is like to be interacting with a database
        - for each functionality, list the common vulnerabilities that are associated with it eg: file upload functions may be vulnerable to path traversal, inter-user message may be vulnerable to XSS, Contact Us functions may be vulnerable to SMTP injection
3) - [] Test Client-Side Controls
    3.1) Test Transmission of Data Via the Client
    3.2) Test Client-Side Controls Over User Input
    3.3) Test Browser Extension Components
4) - [] Test the Authentication Mechanism
    4.1) Understand the Mechanism
    4.2) Test Password Quality
    4.3) Test for User Enumeration
    4.4) Test Resilience to Password Guessing
    4.5) Test any Account Recovery Function
    4.6) Test Any Remember Me Function
    4.7) Test Any Impersonation Function
    4.8) Test Username Uniqueness
    4.9) Test Predictability of Autogenerated Credentials
    4.10) Check for Unsafe Transmission of Credentials
    4.11) Check for Unsafe Distribution of Credentials
    4.12) Test for Insecure Storage
    4.13) Test for Logic Flaws
    4.14) Exploit Any Vulnerabilities
5) - [] Test the Session Management Mechanism
    5.1) Understand the Mechanism
    5.2) Test Token for Meaning
    5.3) Test Token for Predictability
    5.4) Check for Insecure Transmission of Tokens
    5.5) Check for Disclosure of Tokens in Logs
    5.6) Check Mapping of Tokens to Sessions
    5.7) Test Session Termination
    5.8) Check for Session Fixation
    5.9) Check for CSRF
    5.10) Check Cookie Scope
6) - [] Test Access Controls
    6.1) Understand the Access Control Requirements
    6.2) Test with Multiple Accounts
    6.3) Test with Limited Access
    6.4) Test for Insecure Access Control Methods
7) - [] Test for Input-Based Vulnerabilities
    7.1) Fuzz All Request Parameters
    7.2) Test for SQL Injection
    7.3) Test for XSS and Other Response Injection
    7.4) Test for OS Command Injection
    7.5) Test for Path Traversal
    7.6) Test for Script Injection
    7.7) Test for File Inclusion
8) - [] Test for Function-Specific Input Vulnerabilities
    8.1) Test for SMTP Injection
    8.2) Test for Native Software Vulnerabilities
    8.3) Test for SOAP Injection
    8.4) Tets for LDAP Injection
    8.5) Test for XPath Injection
    8.6) Test for Back-End Request Injection
    8.7) Test for XXE Injection
9) - [] Test for Logic Flaws
    9.1) Identify the key Attack Surface
    9.2) Test Multistage Processes
    9.3) Test Handling of Incomplete Input
    9.4) Test Trust Boundaries
    9.5) Test Transaction Logic
10) - [] Test for Shared Hosting Vulnerabilities
    10.1) Test Segregation in Shared Infrastructures
    10.2) Test Segregation Between ASP-Hosted Applications
11) - [] Test for Application Server Vulnerabilities
    11.1) Test for Default Credentials
    11.2) Test for Default Credentials
    11.3) Test for Dangerous HTTP Methods
    11.4) Test for Proxy Functionality
    11.5) Test for Virtual Hosting Misconfiguration
    11.6) Test for Web Server Software Bugs
    11.7) Test for Web Application Firewalling
12) - [] Miscellaneous Checks
    12.1) Check for DOM-Based Attacks
    12.2) Check for Local Privacy Vulnerabilities
    12.3) Check for Weak SSL Ciphers
    12.4) Check Same-Origin Policy Configuration
13) Follow up any information leakage