# SteelheadLodge.com — GitHub Pages Setup

## Overview

Static lodge site hosted on GitHub Pages at **steelheadlodge.com**.  
Preview: https://steelheadlodge.github.io/steelhead-lodge/

Sister site: **salmonrivertubing.com** (tubing-focused landing).

---

## Repo

- **GitHub:** `steelheadlodge/steelhead-lodge`
- **Branch:** `main` (root)
- **CNAME:** `steelheadlodge.com`
- **Contact form:** Formspree `https://formspree.io/f/xeenawba`

---

## GitHub Pages

1. Push `main` (includes `CNAME` file).
2. **Settings → Pages:** source **main** / **(root)**.
3. **Custom domain:** `steelheadlodge.com` → wait for DNS check → enable **Enforce HTTPS**.

---

## DNS — Network Solutions (`steelheadlodge.com`)

Same pattern as doortronix.com. **Keep email CNAMEs** (mail, imap, pop, smtp → netsolmail.net).

### A records (@) — four GitHub Pages IPs

| Host | Points to        |
|------|------------------|
| @    | 185.199.108.153  |
| @    | 185.199.109.153  |
| @    | 185.199.110.153  |
| @    | 185.199.111.153  |

### CNAME

| Host | Points to                |
|------|--------------------------|
| www  | steelheadlodge.github.io |

**Remove** old website hosting:

- Delete any **`*` A** or **`@` A** pointing to Network Solutions web builder (e.g. `206.188.x.x`).
- Do **not** remove email records.

Propagation: 15–60 minutes typical; up to 24h. Then click **Check again** in GitHub Pages settings.

---

## After cutover

- [ ] Confirm https://steelheadlodge.com and https://www.steelheadlodge.com in incognito
- [ ] Cancel Network Solutions **website builder only** (keep domain, DNS, email)
- [ ] Test reservation form → Formspree inbox

---

## Push changes

```bash
cd "/Users/ai/Documents/SteelheadLodgeBusiness/steelhead-lodge"
git add index.html CNAME GITHUB-SETUP.md thankyou.html .gitignore
git commit -m "Prepare steelheadlodge.com launch: pricing sync and GitHub Pages DNS"
git push
```
