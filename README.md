

# 🔓 SQL Injection Demo: Exploiting and Mitigating Classic Patterns

## 🧠 Objective

This project demonstrates the exploitation of common SQL injection patterns in a controlled, educational lab environment. Each pattern is paired with its triggering payload, the corresponding vulnerable query, and a breakdown of detection and mitigation strategies. The goal is to raise awareness about insecure query handling and emphasize robust defensive techniques.

---

## 🚨 Injection Patterns Simulated

| Pattern                       | Injection String                                | Purpose                                  |
|------------------------------|--------------------------------------------------|------------------------------------------|
| Authentication Bypass        | `' OR '1'='1' --`                                | Circumvents login logic to gain access   |
| Union-Based Data Leakage     | `1' UNION SELECT username, password FROM users --` | Extracts data from unrelated tables     |
| Second-Order Injection       | `Nice post' OR '1'='1' --`                       | Triggers injection from previously stored input |
| Blind Injection via Delay    | `1 AND IF('a'='a', SLEEP(5), 0) --`             | Confirms vulnerability by response timing |
| Stacked Queries              | `John'; DROP TABLE users; --`                   | Executes multiple statements, destructive |



<img width="330" height="330" alt="image" src="https://github.com/user-attachments/assets/15fd3fd4-4b05-40ea-ac2b-a69a6eaf7d98" />
<img width="330" height="330" alt="image" src="https://github.com/user-attachments/assets/e48fce02-b6f3-473f-a187-358c7df2f3bf" />
<img width="330" height="330" alt="image" src="https://github.com/user-attachments/assets/35077d62-ad93-4cd9-9c13-2de64491ecf2" />
<img width="330" height="330" alt="image" src="https://github.com/user-attachments/assets/c3090499-8668-41d9-bf88-4afae52eb894" />
<img width="330" height="330" alt="image" src="https://github.com/user-attachments/assets/23c1a49b-6fab-4f54-93a0-74072c594159" />


---

## 🧪 Detection Tool Behavior

Each payload activates a pattern-matching engine designed to identify:
- Logical anomalies in `WHERE` clauses (e.g. `'1'='1'`)
- Use of SQL keywords (`UNION`, `DROP`, `CONVERT`, `SLEEP`)
- Multi-statement execution (`;`)
- Deliberate syntax errors and timing functions

Detected patterns are highlighted visually—red flags denote **authentication threats**, orange for **data exposure**, and purple for **behavioral-based exploits**.

---

## 🔐 Mitigation Strategies

To defend against SQL injection:
- Use **parameterized queries** or **prepared statements**
- Sanitize and validate user input (e.g. reject suspicious characters)
- Restrict error messages and avoid exposing stack traces
- Implement query whitelisting where possible
- Log unusual input behaviors for audit


---

## 📜 Ethical Disclaimer

All injections were performed against intentionally vulnerable inputs in a test built for detection and documentation. This is not intended for use against live systems.


---
