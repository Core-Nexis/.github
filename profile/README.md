<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Core-Nexis/.github/main/profile/assets/corenexis-wordmark-dark.png">
  <img src="https://raw.githubusercontent.com/Core-Nexis/.github/main/profile/assets/corenexis-wordmark-light.png" alt="Corenexis" width="300">
</picture>

<h3>Developer APIs, secure sign-in, and the Cashly money app.</h3>

Production REST APIs on one key, OAuth 2.0 sign-in with two-factor built in, and a personal finance app
that AI assistants can work with - each with an MCP server for agents.

<br>

[![Website](https://img.shields.io/badge/corenexis.com-000B36?style=for-the-badge)](https://corenexis.com)
[![Corenexis API](https://img.shields.io/badge/Corenexis_API-FE5940?style=for-the-badge)](https://api.corenexis.com)
[![Corenexis OAuth](https://img.shields.io/badge/Corenexis_OAuth-000B36?style=for-the-badge)](https://corenexis.com/oauth)
[![Cashly](https://img.shields.io/badge/Cashly-FE5940?style=for-the-badge)](https://cashly.corenexis.com)

![REST](https://img.shields.io/badge/REST-JSON-5A6480?style=flat-square)
![OAuth 2.0](https://img.shields.io/badge/OAuth_2.0-PKCE_%2B_2FA-5A6480?style=flat-square)
![MCP](https://img.shields.io/badge/MCP-Official_Registry-15705A?style=flat-square)
![n8n](https://img.shields.io/badge/n8n-community_nodes-5A6480?style=flat-square)

<br>

<img src="https://raw.githubusercontent.com/Core-Nexis/.github/main/profile/assets/corenexis-banner.jpg" alt="Corenexis - APIs, sign-in and apps, built secure" width="820">

</div>

<br>

## What we build

<table>
<tr>
<td width="33%" valign="top">

<img src="https://raw.githubusercontent.com/Core-Nexis/.github/main/profile/assets/corenexis-api-icon.png" width="56" height="56" alt="Corenexis API">

### Corenexis API

**[api.corenexis.com](https://api.corenexis.com)**

9+ production REST APIs for documents, images and data quality. One key, one header, predictable JSON,
and a free tier on every API.

`Markdown to PDF` `HTML to PDF` `OCR` `Email validation` `Image CDN` `QR & barcode`

MCP server: `com.corenexis/api`

**[Docs and MCP guide →](https://github.com/Core-Nexis/corenexis-api)**

</td>
<td width="33%" valign="top">

<img src="https://raw.githubusercontent.com/Core-Nexis/.github/main/profile/assets/corenexis-oauth-icon.png" width="56" height="56" alt="Corenexis OAuth">

### Corenexis OAuth

**[corenexis.com/oauth](https://corenexis.com/oauth)**

Secure sign-in for your app in one OAuth 2.0 integration: Google, GitHub, Microsoft, magic link and
password, with TOTP two-factor, a consent screen and device management already built in.

RS256 JWTs · JWKS · PKCE · refresh rotation with reuse detection · no SDK to install

**[Integration guide →](https://corenexis.com/oauth)**

</td>
<td width="33%" valign="top">

<img src="https://raw.githubusercontent.com/Core-Nexis/.github/main/profile/assets/cashly-icon.png" width="56" height="56" alt="Cashly">

### Cashly

**[cashly.corenexis.com](https://cashly.corenexis.com)**

A free expense, EMI and debt tracker for Android and web, in any currency, with no bank login. Manage
it by chat: a REST API, webhooks and an MCP server let ChatGPT, Claude or n8n read and log entries.

MCP server: `com.corenexis/cashly`

**[API and MCP guide →](https://github.com/Core-Nexis/cashly)**

</td>
</tr>
</table>

<br>

## For developers and AI agents

| | Repository | What is inside |
|---|---|---|
| Corenexis API | [`Core-Nexis/corenexis-api`](https://github.com/Core-Nexis/corenexis-api) | REST reference, MCP setup for every client, examples |
| Cashly | [`Core-Nexis/cashly`](https://github.com/Core-Nexis/cashly) | MCP server, REST API, webhooks, examples |
| n8n | [`n8n-nodes-cashly`](https://github.com/Core-Nexis/n8n-nodes-cashly) · [`n8n-nodes-corenexis-api`](https://github.com/Core-Nexis/n8n-nodes-corenexis-api) | Community nodes for n8n workflows |

Both MCP servers are listed on the [Official MCP Registry](https://registry.modelcontextprotocol.io/v0/servers?search=com.corenexis)
and run remotely over Streamable HTTP - nothing to install.

<br>

## Quick start

**Call any API** - one header is the whole authentication story.

```bash
curl -X POST https://api.corenexis.com/email-validator/v1 \
  -H "x-api-key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"email": "hello@corenexis.com"}'
```

**Give an AI assistant the APIs** - add the MCP server to Claude, Cursor, VS Code or any MCP client.

```json
{
  "mcpServers": {
    "corenexis": {
      "type": "http",
      "url": "https://api.corenexis.com/mcp/server",
      "headers": { "x-api-key": "YOUR_API_KEY" }
    }
  }
}
```

**Add secure sign-in to your app** - standard OAuth 2.0 authorization code, no SDK required.

```js
// 1 - send the user to Corenexis
res.redirect('https://accounts.corenexis.com/'
  + '?redirect=' + encodeURIComponent(CALLBACK)
  + '&state=' + state);

// 2 - they come back with ?code=... ; exchange it on your server
const tok = await (await fetch(BASE + '/api/token', {
  method: 'POST',
  body: new URLSearchParams({
    grant_type:    'authorization_code',
    code:          req.query.code,
    client_id:     CLIENT_ID,
    client_secret: CLIENT_SECRET,
  }),
})).json();

// 3 - a verified user, and your app never saw a password
req.session.userId = tok.user.id;
```

<div align="center">
<br>

**Free API key, no credit card** → **[dash.corenexis.com](https://dash.corenexis.com)**

</div>

<br>

---

<div align="center">

<sub>Also from Corenexis: <a href="https://secrets.corenexis.com">Corenexis Secrets</a> (zero-knowledge password vault) and <a href="https://corenexis.com/project-quote">AI automation and development</a> for businesses.</sub>

<br><br>

<sub>

[Website](https://corenexis.com) · [Support](https://helpdesk.corenexis.com) · [Blog](https://blog.corenexis.com) · [Privacy](https://corenexis.com/privacy) · [Terms](https://corenexis.com/terms-of-service) · **contact@corenexis.com**

</sub>

<br>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/corenexis)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=flat-square&logo=facebook&logoColor=white)](https://www.facebook.com/corenexis)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=flat-square&logo=instagram&logoColor=white)](https://www.instagram.com/corenexis)
[![Medium](https://img.shields.io/badge/Medium-000000?style=flat-square&logo=medium&logoColor=white)](https://medium.com/@corenexis)
[![Crunchbase](https://img.shields.io/badge/Crunchbase-0288D1?style=flat-square)](https://www.crunchbase.com/organization/corenexis)

</div>
