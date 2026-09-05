<div align="center">

<h1>
<img src="https://corenexis.com/assets/logo/logo.png" width="30" alt="">&nbsp;&nbsp;Corenexis
</h1>

**Developer APIs, OAuth 2.0 sign-in, and secure apps.**

Production infrastructure you can wire up in an afternoon — nine REST APIs, a full identity platform, and a zero-knowledge vault. Free tiers on everything.

<br>

[![Website](https://img.shields.io/badge/Website-000B36?style=for-the-badge)](https://corenexis.com)
[![API Platform](https://img.shields.io/badge/API_Platform-FE5940?style=for-the-badge)](https://api.corenexis.com)
[![Sign in with Corenexis](https://img.shields.io/badge/OAuth_2.0-000B36?style=for-the-badge)](https://corenexis.com/oauth)
[![Secrets](https://img.shields.io/badge/Secrets-000B36?style=for-the-badge)](https://secrets.corenexis.com)
[![Cashly](https://img.shields.io/badge/Cashly-000B36?style=for-the-badge)](https://cashly.corenexis.com)
[![Blog](https://img.shields.io/badge/Blog-000B36?style=for-the-badge)](https://blog.corenexis.com)

<br>

![REST](https://img.shields.io/badge/REST-JSON-5A6480?style=flat-square)
![OAuth 2.0](https://img.shields.io/badge/OAuth_2.0-RS256_%2B_PKCE-5A6480?style=flat-square)
![Encryption](https://img.shields.io/badge/AES--256--GCM-zero--knowledge-5A6480?style=flat-square)
![MCP](https://img.shields.io/badge/MCP-agent_ready-5A6480?style=flat-square)
![Free tier](https://img.shields.io/badge/free_tier-on_everything-15705A?style=flat-square)

</div>

<br>

## What we build

<table>
<tr>
<td width="50%" valign="top">

### ⚡ API Platform

**[api.corenexis.com](https://api.corenexis.com)**

Nine production REST APIs for documents, images and data quality. One key, one header, predictable JSON — and a permanently free tier on every single one.

`Markdown to PDF` `HTML to PDF` `OCR` `Email validation` `Image CDN` `QR & barcode`

</td>
<td width="50%" valign="top">

### 🔐 Sign in with Corenexis

**[corenexis.com/oauth](https://corenexis.com/oauth)**

One OAuth 2.0 integration gives your users Google, GitHub, Microsoft, magic-link and password sign-in — with TOTP two-factor, a consent screen and device management already built in.

RS256 JWTs · JWKS · refresh rotation with reuse detection · PKCE · no SDK to install

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🛡️ Secrets

**[secrets.corenexis.com](https://secrets.corenexis.com)**

A zero-knowledge vault for passwords, cards, identities, TOTP codes, API keys and encrypted files. Keys are derived on your device with PBKDF2-SHA256 at 600,000 rounds; the server only ever stores ciphertext.

Eight offline recovery keys · cryptographic sharing · team vaults with per-member roles

</td>
<td width="50%" valign="top">

### 💰 Cashly

**[cashly.corenexis.com](https://cashly.corenexis.com)**

A personal finance app for transactions, EMIs, debts, subscriptions and cards — with timezone-aware reminders so nothing slips.

Ships with a REST API **and an MCP server**, so Claude, n8n or your own agent can read and write entries with a key you issue and revoke.

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🧰 Free Tools

**[tools.corenexis.com](https://tools.corenexis.com)**

25+ browser utilities with no signup — security headers checker, DNS record lookup, IP tools, encryption helpers and image utilities.

</td>
<td width="50%" valign="top">

### 🤖 AI Automation & Development

**[Get a quote](https://corenexis.com/project-quote)**

Custom AI agents and workflow automation with n8n, Make.com and Zapier — plus web development and integration work.

</td>
</tr>
</table>

<br>

## The API catalogue

<details>
<summary><b>All nine APIs — click to expand</b></summary>

<br>

| API | What it does | Docs |
| :-- | :-- | :-- |
| **Markdown to PDF** | Print-ready PDF or page images. Tables, task lists, syntax-highlighted code, 13 typefaces, full control over page size and margins. Handles 1,000+ page documents. | [Docs](https://api.corenexis.com/markdown-to-pdf/docs/) |
| **HTML to PDF** | Renders HTML and CSS exactly as a browser does — grid, flexbox, gradients, web fonts, optional JavaScript execution. | [Docs](https://api.corenexis.com/html-to-pdf/docs/) |
| **Image to Text (OCR)** | Photos, screenshots, scans, bills and signage into clean text and markdown. Auto language detection across 30+ languages. | [Docs](https://api.corenexis.com/image-ocr/docs/) |
| **PDF to Text (OCR)** | Scanned PDFs, tables and complex layouts, with page selection and high accuracy across 30+ languages. | [Docs](https://api.corenexis.com/pdf-to-text/docs/) |
| **Email Validator** | Real-time SMTP and catch-all verification, deliverability checks, MX / SPF / DMARC validation, confidence scoring. | [Docs](https://api.corenexis.com/email-validator/docs/) |
| **Disposable Email Detector** | Blocks temporary and fake addresses in real time against a 146,000+ domain database. | [Docs](https://api.corenexis.com/disposable-email-validator/docs/) |
| **Image CDN** | Upload by file or URL, flexible retention, global delivery, hosted viewer and social sharing. | [Docs](https://api.corenexis.com/image-cdn/docs/) |
| **Image Conversion** | Any format to any format across 25+ formats — WebP, AVIF, HEIC, JPEG XL. Animations preserved. | [Docs](https://api.corenexis.com/image-conversion/docs/) |
| **QR Code & Barcode** | Standard QR, UPI payment QRs, and Code128 / EAN-13 / UPC-A barcodes with logo embedding. | [Docs](https://api.corenexis.com/qr-barcode/docs/) |

</details>

<br>

## Quick start

**Call any API** — one header, that's the whole authentication story.

```bash
curl -X POST https://api.corenexis.com/email-validator/v1 \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"email": "hello@corenexis.com"}'
```

**Add sign-in to your app** — standard OAuth 2.0 authorization code, no SDK required.

```js
// 1 — send the user to Corenexis
res.redirect('https://accounts.corenexis.com/'
  + '?redirect=' + encodeURIComponent(CALLBACK)
  + '&state=' + state);

// 2 — they return with ?code=… ; exchange it server-side
const tok = await (await fetch(BASE + '/api/token', {
  method: 'POST',
  body: new URLSearchParams({
    grant_type:    'authorization_code',
    code:          req.query.code,
    client_id:     CLIENT_ID,
    client_secret: CLIENT_SECRET,
  }),
})).json();

// 3 — a verified user, and your app never saw a password
req.session.userId = tok.user.id;
```

<div align="center">
<br>

**Free API key, no credit card** → **[dash.corenexis.com](https://dash.corenexis.com)**

</div>

<br>

---

<div align="center">

<sub>

[Documentation](https://api.corenexis.com) · [Support](https://helpdesk.corenexis.com) · [Privacy](https://corenexis.com/privacy) · [Terms](https://corenexis.com/terms-of-service) · **contact@corenexis.com**

</sub>

<br>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/corenexis)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=flat-square&logo=facebook&logoColor=white)](https://www.facebook.com/corenexis)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=flat-square&logo=instagram&logoColor=white)](https://www.instagram.com/corenexis)
[![Medium](https://img.shields.io/badge/Medium-000000?style=flat-square&logo=medium&logoColor=white)](https://medium.com/@corenexis)

</div>
