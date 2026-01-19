## Hosting
Globally, web hosting is commonly classified into the following **main types**, based on performance, control, scalability, and cost.
1. Shared Hosting
2. VPS Hosting (Virtual Private Server)
3. Dedicated Server Hosting
   
![Image](https://www.dreamhost.com/blog/wp-content/uploads/2024/10/01_hosting_options_shared_vs_vps_vs_dedicated1.webp)
---

## 1. Shared Hosting

**Most common & beginner-friendly**

* Multiple websites share the same server resources
* Lowest cost
* Limited performance and customization

**Best for:** blogs, personal sites, small businesses
**Example use:** portfolio website, basic company site

---

## 2. VPS Hosting (Virtual Private Server)

**More power and control**

* One physical server is split into virtual servers
* Dedicated resources for each user
* Root access available

**Best for:** growing websites, developers, medium traffic sites
**Example use:** web apps, custom software hosting

---

## 3. Dedicated Server Hosting

**Maximum performance & control**

* One entire physical server for one customer
* High performance, full customization
* Most expensive option

**Best for:** large enterprises, high-traffic platforms
**Example use:** banking systems, large e-commerce sites

---

## 4. Cloud Hosting

**Highly scalable & reliable**

* Uses multiple servers instead of one
* Resources scale automatically
* High uptime and fault tolerance

**Best for:** startups, SaaS platforms, fluctuating traffic
**Example use:** streaming platforms, online services

---

## 5. WordPress Hosting (Managed or Unmanaged)

**Optimized for WordPress only**

* Pre-configured servers for WordPress
* Automatic updates, caching, security
* Limited flexibility outside WordPress

**Best for:** bloggers, WordPress businesses
**Example use:** news sites, content-based platforms

---

## 6. Reseller Hosting

**Hosting for hosting businesses**

* Buy hosting resources in bulk
* Resell them to clients under your brand

**Best for:** web designers, agencies
**Example use:** managing client websites

---

## 7. Colocation Hosting

**Enterprise-level infrastructure**

* You own the server hardware
* Hosting provider supplies space, power, cooling, internet

**Best for:** enterprises with in-house servers
**Example use:** corporate data centers

---

## 8. Serverless Hosting (Modern Approach)

**No server management**

* Run code without managing servers
* Pay only for execution time
* Highly scalable

**Best for:** APIs, microservices
**Example use:** backend functions, event-driven apps

---

## Quick Comparison Table

| Hosting Type | Cost        | Performance | Control     | Scalability |
| ------------ | ----------- | ----------- | ----------- | ----------- |
| Shared       | Low         | Low         | Low         | Low         |
| VPS          | Medium      | Medium      | Medium–High | Medium      |
| Dedicated    | High        | Very High   | Full        | Low         |
| Cloud        | Medium–High | High        | Medium      | Very High   |
| WordPress    | Low–Medium  | Optimized   | Limited     | Medium      |
| Reseller     | Medium      | Medium      | Medium      | Medium      |
| Colocation   | Very High   | Very High   | Full        | Low         |
| Serverless   | Variable    | High        | Code-level  | Very High   |

---


## How to host with VPS Hosting (Virtual Private Server)

Hosting a website with **VPS Hosting (Virtual Private Server)** gives you more control, performance, and flexibility than shared hosting. Below is a **clear, global-standard process** used by most VPS providers.

---

## 1. Buy a VPS Plan

Choose a VPS plan from a hosting provider such as **Hostinger**, AWS, DigitalOcean, etc.

When selecting a plan, consider:

* **CPU & RAM** (e.g., 1–2 vCPU, 2–4 GB RAM)
* **Storage** (SSD preferred)
* **Operating System** (Linux is most common)
* **Server location** (closest to your audience)

After purchase, you’ll receive:

* Server IP address
* Username (usually `root`)
* Password or SSH key

---

## 2. Connect to Your VPS (SSH)

You access a VPS using **SSH** (Secure Shell).

### On Linux / macOS:

```bash
ssh root@your_server_ip
```

### On Windows:

* Use an SSH client like PowerShell or PuTTY
* Enter IP, username, and password/key

Once connected, you control the server via the terminal.

---

## 3. Update the Server

Always update packages first:

```bash
apt update && apt upgrade -y
```

This ensures security and stability.

---

## 4. Install a Web Server

You need software to serve websites.

### Common choices:

* **Nginx** (fast & lightweight – recommended)
* **Apache** (easy & widely used)

Example (Nginx):

```bash
apt install nginx -y
```

Check by opening your server IP in a browser — you should see a welcome page.

---

## 5. Install Required Software (Stack)

Depending on your website type:

### For PHP / WordPress sites:

* PHP
* MySQL or MariaDB

Example:

```bash
apt install php php-fpm mysql-server -y
```

### For Node.js / Python apps:

* Install runtime (Node.js, Python, etc.)
* Use a process manager (PM2, Gunicorn)

---

## 6. Upload Your Website Files

You can upload files using:

### Option A: SCP (from local machine)

```bash
scp -r yoursite/ root@your_server_ip:/var/www/
```

### Option B: Git

```bash
git clone your-repo-url
```

### Option C: SFTP

Use tools like FileZilla with:

* Host: server IP
* Protocol: SFTP
* Username & password

---

## 7. Configure the Web Server

Set your website directory and domain.

Example Nginx config:

```bash
/etc/nginx/sites-available/yourdomain
```

Then:

```bash
ln -s /etc/nginx/sites-available/yourdomain /etc/nginx/sites-enabled/
nginx -t
systemctl reload nginx
```

---

## 8. Point Your Domain to the VPS

At your domain registrar:

* Set **A Record**
* Point it to your VPS IP address

Example:

```
yourdomain.com → your_server_ip
```

DNS propagation may take a few minutes to hours.

---

## 9. Enable SSL (HTTPS)

Secure your site with a free SSL certificate:

```bash
apt install certbot python3-certbot-nginx -y
certbot --nginx
```

Your site will now load with **https://**

---

## 10. Secure the VPS (Very Important)

Basic security steps:

* Change default SSH port
* Disable root login
* Enable firewall:

```bash
ufw allow OpenSSH
ufw allow 'Nginx Full'
ufw enable
```

---

## 11. Maintain & Monitor

Ongoing VPS management includes:

* Regular updates
* Backups
* Monitoring CPU/RAM usage
* Scaling resources as traffic grows


### VPS Hosting — **Short Process Summary**

1. **Buy a VPS** – choose plan, OS, and server location (e.g., from **Hostinger**)
2. **Connect via SSH** – log in using server IP and credentials
3. **Update server** – install latest system updates
4. **Install web server** – Nginx or Apache
5. **Install required stack** – PHP/MySQL, Node.js, Python, etc.
6. **Upload website files** – via SCP, SFTP, or Git
7. **Configure web server** – set domain and root folder
8. **Point domain to VPS** – add DNS A record
9. **Enable SSL** – install free HTTPS (Let’s Encrypt)
10. **Secure & maintain** – firewall, updates, backups

👉 **Flow:**
**VPS Purchase → SSH Access → Server Setup → Website Upload → Domain + SSL → Security**

