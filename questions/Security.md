# Security Questions

## 1. What is SQL injection?

SQL injection is a type of security vulnerability that occurs in an application's data layer, where an attacker can insert or "inject" malicious SQL statements into an otherwise benign SQL query.

### How It Happens

- **User Input Manipulation:** It typically happens when user input is not properly sanitized and is directly used in constructing SQL queries.
- **Example:** A basic example is a login form where the attacker inputs malicious SQL code into the username or password fields.

### Impact

- **Data Breach:** Can lead to unauthorized access to sensitive data such as usernames, passwords, and credit card details.
- **Data Loss or Corruption:** Might result in the deletion or alteration of important data.
- **System Compromise:** In severe cases, can lead to complete system compromise.

### Prevention Techniques

1. **Use Prepared Statements (Parameterized Queries):** They ensure that an attacker cannot change the intent of a query, even if SQL commands are inserted by an attacker.
2. **Use Stored Procedures:** They can encapsulate the SQL logic and prevent direct access or manipulation.
3. **Input Validation:** Ensure rigorous validation checks (like type, pattern, length) on all user input.
4. **Escaping User Input:** If parameterized queries are not possible, ensure user input is properly escaped.
5. **Least Privilege:** Ensure that the database user used by the application has the least privileges necessary.
6. **Regularly Update and Patch:** Keep the database system and software up to date with the latest patches.

## 2. What is XSS?

Cross-Site Scripting (XSS) is a security vulnerability that allows an attacker to inject malicious scripts into content from otherwise trusted websites. XSS attacks occur when an application includes untrusted data in a web page without proper validation or escaping.

### Types of XSS Attacks

1. **Reflected XSS:** The malicious script comes from the current HTTP request. Typically, the attacker tricks a user into clicking a link that contains the script.
2. **Stored XSS:** The malicious script is stored on the target server, such as in a database, and is then presented to users within the web application.
3. **DOM-based XSS:** The vulnerability exists in the client-side code rather than the server-side. The attack occurs when the web application's client-side script writes user-provided data to the Document Object Model (DOM).

### Impact

- **Cookie Theft:** Attacker can steal session tokens or other sensitive information stored in cookies.
- **Phishing:** Display fake login prompts or other content to trick users into revealing sensitive information.
- **Page Defacement:** Modify the appearance of the web page.
- **Remote Code Execution:** In severe cases, execute malicious code on the user’s browser.

### Prevention Techniques

1. **Data Sanitization:** Escaping user input to ensure that it is treated as data, not as code.
2. **Content Security Policy (CSP):** Implementing CSP headers to restrict sources of executable scripts.
3. **Validate Input:** Implementing rigorous validation for all user inputs.
4. **Use Secure Frameworks:** Using frameworks that automatically escape XSS by design.
5. **Regularly Update Libraries:** Keeping all libraries and frameworks up to date.

## 3. How can you stop your DBA from making off with a list of your users’ passwords?

This is an open question that has no single correct answer. The interviewer is looking for a discussion of the tradeoffs between different approaches. Things that we want to here here are:
- Least privilege
- Encryption
- Hashing
- Salting
- Key management
- Access control
- Logging
- Auditing

## 4. What is Cross-Site Request Forgery (CSRF)?

- Cross-Site Request Forgery (CSRF) is an attack that forces an end user to execute unwanted actions on a web application in which they're currently authenticated. CSRF attacks specifically target state-changing requests, not theft of data, since the attacker has no way to see the response to the forged request.
- With a little help of social engineering (such as sending a link via email or chat), an attacker may trick the users of a web application into executing actions of the attacker's choosing.
- If the victim is a normal user, a successful CSRF attack can force the user to perform state changing requests like transferring funds, changing their email address, and so forth. If the victim is an administrative account, CSRF can compromise the entire web application.

## 5. What is parameter tampering?

Parameter tampering is a form of web security vulnerability where an attacker manipulates parameters exchanged between client and server in order to modify application data, such as user credentials and permissions, prices in e-commerce sites, etc. This manipulation can occur in various ways, including altering hidden fields or query strings in URLs.

### How It Happens

- **Manipulating URLs:** Changing query parameters in the URL.
- **Editing Hidden Fields:** Altering hidden form fields before submission.
- **Cookie Tampering:** Modifying cookies stored by the browser.
- **HTTP Header Manipulation:** Changing headers sent in the HTTP request.

### Impact

- **Unauthorized Access:** Gaining access to other users' data or administrative functions.
- **Data Theft:** Stealing or manipulating sensitive information.
- **Fraud:** Altering prices or quantities in e-commerce transactions.

### Prevention Techniques

1. **Validation on Server-Side:** Ensure all data received from the client is validated on the server side.
2. **Use of Session Variables:** Store important data in server-side session variables instead of sending it back and forth to the client.
3. **Avoid Revealing Sensitive Information:** Minimize the use of sensitive information in parameters, especially in visible ones like URL query parameters.
4. **HTTPS:** Use HTTPS to encrypt data in transit, preventing tampering during transmission.
5. **Regular Security Audits:** Conduct security audits and penetration testing to identify and fix vulnerabilities.

## 6. What is a DoS attack? And what is a DDoS attack?

### DoS Attack

- **Definition:** A Denial of Service (DoS) attack is a cyber-attack where the attacker seeks to make a machine or network resource unavailable to its intended users by temporarily or indefinitely disrupting services of a host connected to the Internet.
- **Method:** This is typically accomplished by overwhelming the target with a flood of network packets, requests, or other inputs in a way that the system cannot cope with.
- **Impact:** The result is that legitimate users cannot access the service, such as a website or web application.

### DDoS Attack

- **Definition:** A Distributed Denial of Service (DDoS) attack is a type of DoS attack where multiple compromised computer systems, often infected with a Trojan, are used to target a single system.
- **Method:** The influx of incoming messages, connection requests, or malformed packets to the target system forces it to slow down or even crash and shut down, thereby denying service to legitimate users.
- **Scale:** DDoS attacks are often global in scale, using botnets (networks of compromised computers) to execute widespread attacks against a target.

### Differences

- **Scale and Origin:** The primary difference between the two is scale. A DoS attack typically comes from one source, while a DDoS attack comes from multiple locations, often globally distributed, making it harder to stop.
- **Intensity and Complexity:** DDoS attacks are generally more complex and intense, as they utilize the combined computing power of numerous infected machines.
