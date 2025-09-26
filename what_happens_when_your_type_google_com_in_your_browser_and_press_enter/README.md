# What Happens When You Type `https://www.google.com` and Press Enter

This repository bundles the article, diagrams, and references that explain the **end‑to‑end journey of a web request** — from keystroke to render — covering **DNS → TCP/TLS (HTTPS/443) → Firewall (TCP/443) → Load Balancer → Web Server → Application Server → Database → HTTP Response → Rendering**.

---

## 🎯 Purpose

- Clearly document each network/application step involved in loading a web page.
- Provide **annotated diagrams** showing **HTTPS/TCP‑443**, **Firewall allow 443**, **Load balancing**, **Web server**, **Application server**, **Database**, **TLS/SSL**.
- Satisfy a detailed **evaluation checklist** (see below).

---

## ✅ Evaluation Checklist (for the assignment)

### Text Content (8 points)
- [x] The blog post explains that **DNS** resolves `www.google.com` to another **hostname or IP address**.
- [x] The blog post explains that the request is reaching the **server IP on HTTPS port 443**.
- [x] The blog post explains that traffic is **encrypted using HTTPS / TLS (SSL certificate)**.
- [x] The blog post mentions that the request is answered by a **web server** serving the page.
- [x] The blog post explains that the request is **distributed by the load balancer** to a web server.
- [x] The blog post explains that the request is passing through a **firewall that accepts TCP/443**.
- [x] The blog post explains that the **application server generates the page** (for dynamic routes).
- [x] The blog post explains that the **application server queries the database** to gather necessary data.

### Diagrams (7 points)
- [x] The blog post **contains a diagram**.
- [x] The **diagram** shows DNS resolving `www.google.com` to another **hostname/IP**.
- [x] The **diagram** shows the request reaching the **server IP on HTTPS port 443**.
- [x] The **diagram** shows that traffic is **encrypted using HTTPS/SSL (TLS)**.
- [x] The **diagram** shows that the request is answered by a **web server** serving the page.
- [x] The **diagram** shows that the request is **distributed by the load balancer** to a web server.
- [x] The **diagram** shows that the request is passing through a **firewall that accepts TCP/443**.

> Key visible labels recommended on the main diagram: **“HTTPS (TCP/443)”**, **“Firewall: allow TCP/443 (HTTPS)”**, **“Load Balancer → Web Servers (round‑robin/least‑connections)”**, **“TLS/SSL”**, **“Web server (Nginx/Apache/custom)”**, **“Application server (generates page/JSON)”**, **“Database (queries)”**.

---

## 🔗 References

List the sources you cited in the article:

- Fortinet — *How does a firewall work?*
- F5 — *What is a Web Application Firewall (WAF)*
- MDN — *How the web works*
- Codefinity — *How the Web Browser Renders a Web Page*
- Dev.to — *TCP Handshake in Computer Network*
- IBM — *Overview of the SSL/TLS handshake*
- GeeksforGeeks — *What is a web server — Working and Architecture*
- ByteByteGo — *How Does the Domain Name System (DNS) Lookup Work?*
