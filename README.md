# **BurpSuite Brute-Force Attack Lab**

## **Overview**
This project demonstrates a complete real-world brute-force attack workflow using **BurpSuite Community Edition** against a vulnerable login form hosted on **OWASP BWA**.  
The goal of the exercise is to show how weak authentication mechanisms can be exploited when applications fail to enforce proper security controls.

---

## **What This Project Covers**

### **1. Configuring Browser Traffic Through BurpSuite**
Ensuring all HTTP requests pass through Burp by setting up a manual proxy in Firefox.

### **2. Intercepting & Analyzing HTTP Login Requests**
Capturing raw request data to study parameters, headers, and server behavior.

### **3. Identifying Injectable Parameters**
Locating username and password fields that can be manipulated using Burp Intruder.

### **4. Executing a Cluster Bomb Attack**
Using **Burp Intruder’s Cluster Bomb mode** to test numerous username/password combinations automatically.

### **5. Automating Success Detection with Grep Extraction**
Leveraging **Grep - Extract** to detect successful login attempts by analyzing redirect patterns (e.g., `login.php` → `index.php`).

### **6. Understanding Server Redirect Behavior**
Recognizing how page transitions and response codes reveal valid credentials.

### **7. Evaluating Authentication Weaknesses**
Highlighting common failures:
- No rate limiting  
- No account lockout  
- No CAPTCHA  
- No monitoring  
- Predictable responses  

---

## **Tools & Technologies Used**

### **Core Tools**
- **BurpSuite Community Edition**  
- **Firefox Proxy Configuration**  
- **OWASP Broken Web Applications (BWA)**  
- **DVWA (Damn Vulnerable Web Application)**  

### **Skills Demonstrated**
- **HTTP request/response analysis**  
- **Intruder payload configuration**  
- **Authentication attack methodology**  
- **Practical offensive security thinking**

---

## **Summary**
This lab reflects a realistic attacker workflow and showcases essential penetration-testing skills.  
It demonstrates your ability to:

- Analyze web applications  
- Exploit vulnerable authentication mechanisms  
- Automate attacks using industry-standard tools  
- Document security testing clearly and professionally  

Perfect for a cybersecurity portfolio or GitHub showcase.
