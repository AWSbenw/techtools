# TechTools Hub 🛠️

A lightweight, single-file web app providing a collection of useful IT and networking tools. No build step, no dependencies to install — just open the HTML file or host it anywhere.

## Tools

### 🌐 Subnet Calculator
Calculate network ranges from CIDR notation, split subnets, recombine them, and visualise the full subnet hierarchy as an interactive tree.

### 📶 WiFi QR Generator
Generate a scannable QR code for any WPA WiFi network. Download as PNG or print as a PDF handout — useful for offices, events, or home networks.

### 📈 Uptime Nines Calculator
Convert an uptime percentage to maximum allowable downtime (and vice versa). Includes SLA tier reference and preset buttons for 99% through 99.99999%.

### 🌐 Network Latency Tester
Test TCP latency to any hostname or IP address using WebSocket handshake timing. Includes presets for common AWS regions, Cloudflare DNS, and Google DNS. Add your own endpoints, run tests, and compare results side-by-side.

---

## Features

- **Zero build step** — single HTML file, all dependencies loaded from CDN
- **Dark mode** — site-wide toggle in the nav bar
- **S3 / GitHub Pages ready** — upload and serve, nothing else required
- **No tracking, no ads, no external data collection**

## Tech Stack

| Library | Purpose |
|---|---|
| React 18 | UI components |
| Tailwind CSS (CDN) | Utility styling |
| Babel Standalone | In-browser JSX transpilation |
| QRCode.js | WiFi QR code generation |

## Deployment

### GitHub Pages

1. Rename `index.html` (if not already)
2. Push to a GitHub repository
3. Go to **Settings → Pages → Source** and select the `main` branch
4. Your site will be live at `https://USERNAME.github.io/REPO-NAME/`

### AWS S3 Static Hosting

```bash
# Upload
aws s3 cp index.html s3://your-bucket-name/index.html --content-type "text/html"

# Enable static website hosting
aws s3 website s3://your-bucket-name/ --index-document index.html
```

Make sure your bucket policy allows public `s3:GetObject`, or restrict access via CloudFront + OAC.

### Local

Just open `index.html` in any modern browser. No server required.

## Adding More Tools

Each tool is a self-contained React component. To add a new one:

1. Write the component in the `<script type="text/babel">` block
2. Add a tile entry to the `TOOLS` array
3. Add a render entry to the `App` function

## Useful Software Links

The home page includes a curated links section for useful IT software. Edit the `SOFTWARE_LINKS` array in the script to add categories and links.

---

> Results from the Network Latency Tester and other diagnostic tools are indicative only. Not affiliated with AWS, Cloudflare, or any other referenced service.
