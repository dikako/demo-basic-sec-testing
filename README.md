# QA Security Training Simulator

A lightweight, interactive web application designed to help QA engineers and developers understand common Web Security Vulnerabilities.

This single-page application simulates real-world security bugs (**Vulnerable Mode**) and demonstrates how they should function when fixed (**Secure Mode**).

## 🚀 Features / Scenarios

The simulator covers four major security flaws commonly found in web applications:

1.  **Data Exposure (Sensitive Data Leak)**
    *   **Vulnerable**: API returns excessive data (SSN, Password Hash) hidden in the JSON response even if the UI doesn't show it.
    *   **Secure**: API returns a DTO (Data Transfer Object) with only the necessary public fields.

2.  **IDOR (Insecure Direct Object Reference)**
    *   **Vulnerable**: A user can access another user's private profile simply by changing the ID URL parameter (e.g., `?id=102`).
    *   **Secure**: The backend checks if the logged-in user is authorized to view the requested resource (returns 403 Forbidden).

3.  **Stored XSS (Cross Site Scripting)**
    *   **Vulnerable**: Identifying inputs are trusted. Malicious scripts (e.g., `<script>alert(1)</script>`) are saved and executed in the browser.
    *   **Secure**: Inputs are sanitized or output encoded (treated as text, not HTML).

4.  **SQL Injection (Authentication Bypass)**
    *   **Vulnerable**: User input is concatenated directly into SQL queries (`SELECT ... WHERE user = '$input'`). Attackers can login as Admin using payloads like `admin' --`.
    *   **Secure**: Uses Parameterized Queries (Prepared Statements) to treat input strictly as data, neutralizing the attack.

## 🛠️ How to Use

1.  **Toggle the Mode**:
    *   Use the switch at the top to toggle between **RED (Vulnerable)** and **GREEN (Secure)** modes.
2.  **Select a Scenario**:
    *   Click through the tabs (1-4) to explore different vulnerabilities.
3.  **Run the Test**:
    *   Follow the instructions in the blue "Info Box" for each tab to trigger the bug or verify the fix.

## 📦 Installation & Deployment

### Run Locally
Simply open `index.html` in any web browser. No server or backend installation required! The "backend" and "database" are simulated entirely in JavaScript for training purposes.

## 📝 License
Free to use for educational and training purposes.
