# What Happens When You Type `https://www.google.com` and Press Enter

This repository bundles the article, diagrams, and references that explain the **end‑to‑end journey of a web request** — from keystroke to render — covering **DNS → TCP/TLS (HTTPS/443) → Firewall (TCP/443) → Load Balancer → Web Server → Application Server → Database → HTTP Response → Rendering**.

---

## 🎯 Purpose

- Clearly document each network/application step involved in loading a web page.
- Provide **annotated diagrams** showing **HTTPS/TCP‑443**, **Firewall allow 443**, **Load balancing**, **Web server**, **Application server**, **Database**, **TLS/SSL**.
- Satisfy a detailed **evaluation checklist** (see below).

---

## 🗂️ Repository Structure

> Adjust names if your files differ. If you have the source files of the diagrams (Excalidraw, draw.io, Mermaid), include them too.

```
.
├── README.md                          # You are here
├── article/
│   ├── what-happens-when-you-type.md  # Markdown version of the article
│   └── sources.md                     # Reference links (Fortinet, F5, MDN, etc.)
├── diagrams/
│   ├── network-flow.png               # Main annotated diagram
│   ├── tls-handshake.png              # TLS handshake diagram (optional)
│   ├── dns-lookup.png                 # DNS lookup diagram (optional)
│   └── diagram-notes.txt              # Diagram captions/notes
├── assets/                            # (optional) fonts/illustrations
└── tools/
    └── export-notes.md                # (optional) how to edit/regenerate diagrams
```

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

## ▶️ Local Viewing

### 1) Read the article in Markdown
Open `article/what-happens-when-you-type.md` in your Markdown viewer (VS Code works great).

### 2) Serve images locally (optional)
If you want a quick local preview (static hosting for images/HTML):

```bash
# Python 3.x
python -m http.server 8080
# then open http://localhost:8080 in your browser
```

---

## ✍️ Editing the Diagrams

- **Recommended tools:** Excalidraw, draw.io, or Mermaid.
- **Golden rule:** keep labels **short and visible** (e.g., “HTTPS (TCP/443)”, “Firewall allow 443”).
- If using Mermaid, store the `.mmd` sources alongside the exported `.png` files.

Example of `diagrams/diagram-notes.txt`:

```
Diagram notes:
- Inbound traffic is HTTPS over TCP/443, allowed at the edge firewall
- The load balancer forwards requests to web servers
- Dynamic routes go to an application server, which may query a database
```

---

## 🔗 References

List the sources you cited in the article (place full URLs in `article/sources.md`):

- Fortinet — *How does a firewall work?*
- F5 — *What is a Web Application Firewall (WAF)*
- MDN — *How the web works*
- Codefinity — *How the Web Browser Renders a Web Page*
- Dev.to — *TCP Handshake in Computer Network*
- IBM — *Overview of the SSL/TLS handshake*
- GeeksforGeeks — *What is a web server — Working and Architecture*
- ByteByteGo — *How Does the Domain Name System (DNS) Lookup Work?*

---

## 🤝 Contributing

1. Fork this repository.
2. Create a feature branch: `git checkout -b feat/your-change`.
3. Commit with a clear message: `feat: clarify firewall policy (allow TCP/443)`.
4. Open a Pull Request and, if you changed diagrams, attach updated screenshots.

---

## 🧪 Optional Checks

- Lint Markdown (e.g., `markdownlint`).
- Verify that **all images** in `diagrams/` are referenced in the article.
- (Optional) Add a tiny script to assert keyword presence in the article (helps avoid regressions): `443`, `Firewall`, `Load balancer`, `Application server`, `Database`.

---

## 📄 License

MIT (or the license of your choice). Add a `LICENSE` file at the repository root.

---

## 📝 Changelog

- **2025‑09‑27**: Added sections *HTTPS/443*, *Firewall policy*, *Web vs App server*, *Fetching from DB*; updated diagrams with **TCP/443 / TLS / LB / Firewall** annotations.
