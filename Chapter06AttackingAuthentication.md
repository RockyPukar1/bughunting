159-177
1) - [x] Authentication Tehchnologies
2) - [x] Design Flaws in Authentication Mwechanisms
    1) Bad Passwords
        - ability to assign weak password by bypassing client side validation, is not considered a vulnerability
    2) Brute-Forcible Login
        - 302 redirection is mostly a successful bruted password
        - bad login attempts to see error message
        - after 10 failed login if message about account locking not received then login in correctly. If succeeded, there is no account lockout policy
        - if locked, try with different account and new cookie
        - see after locked, if correct password and wrong password give the same output. If it shows difference then you can continue password guessing even if the account is locked
        - while performing brute forcing, if you have list of username and password, then run change on username and keep the same password for one loop
    3) Verbose Failure Messages
        - username enumeration is done with the help of registration function
        - user comparer tool in burp tool to analyze application reponses
        - see for usernames, email in the code comments
    4) Vulnerable Tranmission of Credentials
        - if credentials are transmitted in query string parameters, in place of body of POST request
        - persistent cookies stored, can escalate previleges
        - find the instance where credentials are submitted in a query string or as a cookie
        - when the actual credentials data are not seen in the request, reverse enginer the obfuscation algorithm to decode the encoded data sent in place
        - if credentials submitted using HTTPS, but Login form loaded as HTTP, vulnerable to man-in-the-middle attack.
    5) Password Change Functionality
        - new password, confirm new password if not allowed then the password already exists
        - check if the password change functionality is only accessible to authenticated user, and if username not included in password change field then there may be a option to include arbitrary username, using the same parameter name of the username, which was hidden field
    6) Forgotten Password Functionality
        - if application doesnot have option to provide email, it may be present in the cookie, so email can be known
        - if recovery email contians recovery link try to infer a pattern on that URL and use it
    7) "Remember Me" Functionality
        - Cookie: RememberUser = daf
        - check if the remember me functionality remembers the username only(hit the password again) or full remembers the user
        - try this with multiple similar username or password, then try to reverse engineer the original data 
    8) User Impersonation Functionality
        - logging other users account from the organization's side
    9) Incomplete Validation of Credentials
        - use your own account change
    10) Nonunique Usernames
        - vulnerable to username enumeration
        - try to register with same username different password, use for username
    11) Predicatible Usernames
        - if application generates username, see sequence or pattern quickly before any other person registers 
    12) Predictable Initial Passwords
    13) Insecure Distribution of Credentials
3) - [z] Implementation Flaws in Authentication
    1) Fail-Open Login Mechanisms
        - observer every valid login, invalid login with multiple and varying datas field leaving some empty some replacement numbers to strings and vice versa
    2) Defects in Multistage Login Mechanisms
        - security question can be removed by removing cookie
    3) Insecure Storage of Credentials
        - online databases of common hashing functionalies are:
            - http://passcracking.com/index.php
            - http://authsecu.com/decrypter-dechiffrer-cracker-hash-md5/
script-hash-md5.php
        - check if the user's password is transmitted back to user -> this indicates password being stored insecurely
4) - [] Securing Authentication
    1) Use Strong Credentials
    2) Handle Credentials Secretively
    3) Validate Credentials Property
    4) Prevent Information Leakage
    5) Prevent Brute-Force Attacks
    6) Prevent Misuse of the Password Change Function
    7) Prevent Misuse of the Account Recovery Function
    8) Log, Monitor, and Notify
