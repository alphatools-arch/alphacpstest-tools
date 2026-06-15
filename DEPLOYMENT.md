# Deployment & Operations

This document describes **how AlphaCPSTest.com is hosted and maintained at a high level.** It is intended as operational documentation and brand transparency.

> **Note:** This document intentionally does **not** include source code, build steps, file contents, or internal implementation details. It describes the hosting and SEO workflow only.

---

## 🌐 Hosting — Netlify

AlphaCPSTest.com is deployed as a **static site on [Netlify](https://www.netlify.com/)**.

**Why Netlify**
- Global CDN delivery for fast load times worldwide
- Automatic HTTPS / SSL (required for the Camera and Microphone tests, which need a secure context)
- Built-in clean-URL handling (extensionless URLs like `/cps-tools`)
- Simple, reliable static hosting with no server to maintain

**Clean URLs**
The site uses extensionless clean URLs throughout (e.g. `/cps-tools`, `/blog/how-to-increase-cps`). Netlify's redirect configuration maps these to the correct pages, keeping the live URLs consistent with the canonical tags used for SEO.

**Custom Domain**
The custom domain `alphacpstest.com` is connected through Netlify's domain settings with HTTPS enforced.

---

## 🔍 Google Search Console Workflow

Search Console is used to manage indexing and monitor search performance.

**1. Property Setup**
- A **Domain property** is verified via DNS, covering all URLs on the domain.

**2. Sitemap Submission**
- The XML sitemap is submitted at: `https://alphacpstest.com/sitemap.xml`
- It lists every indexable page (homepage, hubs, tools, articles hub, guides, and legal pages).

**3. Indexing**
- Priority pages are submitted individually via **URL Inspection → Request Indexing**.
- The remaining pages are discovered automatically through the sitemap.

**4. Monitoring**
- The **Pages** report is checked regularly for indexing status and any coverage issues.
- The **Performance** report tracks impressions, clicks, and average position over time.
- **Core Web Vitals** and **Mobile Usability** reports are monitored for technical health.

---

## 🗺️ sitemap.xml

- Location: `https://alphacpstest.com/sitemap.xml`
- Contains all indexable URLs using clean (extensionless) absolute URLs
- Updated whenever pages are added or removed
- Referenced from `robots.txt` for crawler discovery
- Submitted to both Google Search Console and Bing Webmaster Tools

---

## 🤖 robots.txt

- Location: `https://alphacpstest.com/robots.txt`
- Allows major search engine crawlers full access to public pages
- References the XML sitemap location
- Configured to keep the site fully crawlable while following standard best practices

---

## 📈 Analytics

- **Google Analytics** is used to measure traffic and user behavior across the site.
- Analytics is loaded site-wide for consistent measurement.

---

## 💰 Monetization

- The site is supported by **Google AdSense**.
- This keeps every tool and guide permanently free for all users.

---

## 🔁 Update Workflow (High Level)

1. Content or tools are prepared and tested.
2. The static site is deployed to Netlify.
3. `sitemap.xml` is updated if pages changed.
4. New or updated pages are submitted to Search Console for indexing.
5. Search performance is monitored and iterated on.

---

> For product milestones and version history, see **[CHANGELOG.md](CHANGELOG.md)**.
> For upcoming features, see **[ROADMAP.md](ROADMAP.md)**.
