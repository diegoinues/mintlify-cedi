# Documentation folder layout

This project follows [Mintlify internationalization](https://mintlify.com/docs/guides/internationalization): **one folder per locale**, **mirrored paths** for translated pages, and **shared** template content at the repository root.

**Guide filenames are English slugs** (ASCII, `kebab-case`) so paths are stable and easy to grep. Page **titles** in frontmatter stay in the language of the content (Spanish in `es/`, English in `en/`).

## Locales

| Path | Language | Role |
|------|----------|------|
| `es/` | Spanish | Default locale. Landing: `intro.mdx`; guides: `guides/*.mdx`. |
| `en/` | English | Translations: mirror the **same filename** under `en/guides/` when you translate. |

URLs: `/es/intro`, `/en/intro`, `/es/guides/<slug>`, `/en/guides/<slug>`.

## Guide files (`es/guides/`)

| File | What it covers |
|------|----------------|
| `user-registration-sign-in.mdx` | Alta de cuenta, verificación por correo, inicio de sesión. |
| `business-onboarding-kyc.mdx` | Onboarding persona moral: fiscal, representante, accionistas, PEP, etc. |
| `identity-verification.mdx` | Verificación de identidad (INE, rostro). |
| `registration-flow-figma.mdx` | Diagrama PDF del flujo (Figma). Uses `user-registration-flow.pdf`. |
| `post-login-dashboard.mdx` | Dashboard y navegación tras entrar. |
| `profile-and-2fa.mdx` | Perfil de usuario y configuración 2FA. |
| `transactions-overview.mdx` | Módulo de transferencias (vista general). |
| `domestic-transfers.mdx` | Transferencias nacionales. |
| `international-transfers.mdx` | Transferencias internacionales. |
| `disbursements.mdx` | Dispersiones. |
| `invoices.mdx` | Facturación / centro contable. |
| `invoices-sat.mdx` | Obtención de facturas desde el SAT. |
| `support.mdx` | Soporte / chat. |
| `financial-assistant.mdx` | Agente financiero. |

## Shared (root)

- `essentials/`, `ai-tools/`, `api-reference/` — Mintlify templates (linked from both languages).
- Static images and PDFs: see your paths in MDX (e.g. `/images/...` or `/cedi-imagenes/...` depending on your asset folder).

## Root helpers

- `docs.json` — Navigation and locales.
- `locale-navbar-order.js` — Locale control next to theme toggle.
- `pdfreader.html` — Optional legacy PDF iframe.

## Adding a page

1. Add `es/guides/<english-slug>.mdx` and register `es/guides/<english-slug>` in `docs.json`.
2. When translated, add `en/guides/<english-slug>.mdx` and point the English nav to `en/guides/<english-slug>` for that item.
