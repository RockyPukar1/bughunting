# Web Application Security Assessment Checklist

## 1) Enumerating Content and Functionality

### 1.1) Web Spidering
- [x] **robots.txt**
- [x] Identify REST URLs using the URL path for unique data
- [x] Manually perform form-related operations

### 1.2) User-Directed Spidering
1. **Hack Steps:**
    - a) Manually browse every link, submit forms, and navigate multi-step processes
    - b) Review site maps
    - c) Actively spider using dedicated tools

### 1.3) Discovering Hidden Content
1. Uncover testing and debugging features
2. Identify functionality variations for different user categories
3. Check for old versions still live
4. Test functions for potential database credential exposure
5. Utilize Brute-Force techniques, including:
    - a) GET /$$/ to obtain common directory lists
    - b) Leverage 302 redirection without authentication to access Login Page
    - c) Identify existing directories using 401 Unauthorized or 403 Forbidden responses
    - d) Probe files with predictable names (e.g., /auth/$$Password) for potential vulnerabilities
    - e) Explore HTML forms with disabled SUBMIT buttons
    - f) Leverage Content Discovery features in tools like Burp Suite Pro or DirBuster
    - g) Automatic Fingerprinting based on responses
    - h) Utilize archive.org for snapshots of the website on various dates
    - i) Investigate forums, GitHub issues, or other platforms for potential information leaks
    - j) Employ tools like Nikto and Wikto

### 1.4) Application Page Versus Functional Paths
1. Identify URLs containing function names rather than just page names (e.g., /admin.jsp?action=editUser instead of /admin.jsp/editUser.jsp)
2. Create a comprehensive map of the application using functions and logical paths

### 1.5) Discovering Hidden Parameters
1. Identify parameters like debug, test, hide, source with common values like true, yes, on, 1

## 2) Analyzing the Application

### 2.1) Identifying Entry Points for User Input
- [ ] Query string marker
- [ ] Parameter of body POST request
- [ ] Every cookie
- [ ] HTTP Header User-Agent, Referer, Accept, Accept-Language, Host
    1. **URL File Paths:**
        - a) Consider non-standard parameters
    2. **Request Parameters:**
        - a) Detect payloads inserted in embedded XML data fields for potential SQL injection and path traversal
    3. **HTTP Headers:**
        - a) Scrutinize Referer and User-Agent
        - b) Check X-Forwarded-For for SQL injection and XSS
    4. **Out of Band Channels**

### 2.2) Identifying Server-Side Technologies
1. **Banner Grabbing:**
    - a) Examine the Server HTTP Header
2. **HTTP Fingerprinting:**
    - a) Utilize tools like Httprecon and httprint
3. **File Extensions**
4. **Directory Names**
5. **Session Tokens**
6. **Third-Party Code Components**

### 2.3) Identifying Server-Side Functionality
1. **Dissecting Requests:**
    - a) Example: `https://wahh-app.com/calendar.jsp?name=new%20applicants&isExpired=0&startDate=22%2F09%2F2010&endDate=22%2F03%2F2011&OrderBy=name`
        - eg: `OrderBy` -> SQLi
        - `isExpired = 1` -> Access Control Vulnerability
    - b) Example: `https://wahh-app.com/workbench.aspx?template=NewBranch.tpl&loc=/default&ver=2.31&edit=false`
        - eg: `/default` is a directory and `NewBranch.tlp` is a file -> path traversal attacks
        - eg: `edit=true` -> May allow modification
    - c) Example: `from=user@wahh-mail.com&to=helpdesk@wahh-app.com&subject=Problem+logging+in&message=Please+help...`
        - eg: Email injection
2. **Extrapolating Application Behavior**
3. **Isolating Unique Application Behavior:**
    - Explore debug functions, CAPTCHA controls, usage tracking, and third-party code

### 2.4) Mapping the Attack Surface
1. **Mapping the application:**
    - a) Check client-side validation, database interaction, file uploading, and downloading
    - b) Scrutinize the display of user-supplied data, dynamic redirects, and social networking features
    - c) Assess login mechanisms, session state, access controls, and more
2. [www.osvdb.org](https://www.osvdb.org) -> Check third-party code against the public vulnerability database
