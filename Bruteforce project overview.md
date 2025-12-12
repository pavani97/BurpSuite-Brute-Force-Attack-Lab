# **Objective**
Perform a **brute-force credential attack** against the target’s login form using **BurpSuite** to identify weak or default credentials.

---

# **Attack Walkthrough**
Lab Requirement
Attacker Machine Kali)
Target Machine

## **Step 1 — Access the Target Application**
- Open Firefox on Kali and browse to the target machine’s IP address.  
- Open the **Damn Vulnerable Web Application (DVWA)** login page.

---
![Access Target](assets/image.png)

## **Step 2 — Configure Browser Proxy**
To route traffic through BurpSuite:

1. Open **Firefox Settings**  
2. Search for **proxy**  
3. Choose **Manual Proxy Configuration**  
4. Set:

HTTP Proxy: 127.0.0.1
Port: 8080

This ensures all HTTP requests are captured by BurpSuite.

---

## **Step 3 — Launch BurpSuite**
From the Kali menu, open BurpSuite:

- Click **Next**  
- Click **Start Burp**  
- Open the **Proxy** tab  
- Enable:
Intercept: ON

---

## **Step 4 — Capture Login Request**
Return to Firefox and submit any placeholder credentials:
username: 1
password: 2

BurpSuite immediately captures the raw **HTTP login request**.  
This intercepted request becomes the base for the brute-force attack.

---

## **Step 5 — Send Request to Intruder**
Inside **Proxy → Intercept**:

- Right-click the captured request  
- Select **Send to Intruder**  
- Open the **Intruder** tab

---

## **Step 6 — Configure Attack Positions**
Inside Intruder:

1. Click **Clear** to remove auto-selected injection points  
2. Highlight the value:
username=1

Click **Add**  
3. Highlight the value:
password=2

Click **Add**

Attack Type → Select:
Cluster Bomb

This allows BurpSuite to test every username/password combination.

---

## **Step 7 — Configure Payloads**

### **Payload Set 1 — Usernames**
Add: Test
Guest
admin
root
msfadmin

### **Payload Set 2 — Passwords**
Add:Password@123
P@$$w0rd@123
Admin@123
admin@123
Root@123
admin
root
msfadmin

BurpSuite will now generate all permutations across both lists.

---

## **Step 8 — Start the Attack**
Click:Start Attack → OK

BurpSuite begins sending multiple login attempts.  
However, identifying the correct credentials manually is difficult.

---

## **Step 9 — Identify Successful Login Using Grep Extract**
To detect valid credentials:

1. Open the **Settings** tab in Intruder  
2. Scroll to **Grep - Extract**  
3. Click **Add**  
4. Choose **Fetch response**  
5. Select the response section representing a successful login (from `index.php`)  
6. Rerun the attack

### **Why This Works**
- Invalid login attempts return:
login.php
- Successful logins redirect to:
- index.php
- 
This lets BurpSuite automatically highlight the correct username/password pair.

---

# **Outcome**
BurpSuite successfully performs a brute-force credential attack by analyzing the server’s response patterns and redirect behavior.

This demonstrates a vulnerable authentication system where:

- **No rate limiting** exists  
- **No lockout policies** are implemented  
- **No monitoring or alerting** catches brute-force attempts  

---

# **Final Result**
A full, automated brute-force flow showing how BurpSuite identifies weak credentials using professional penetration testing techniques.















