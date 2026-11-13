# JadanPay Admin Dashboard

Back-office dashboard for the JadanPay owner and staff. It's a single file: `index.html` holds all the markup, styles and script.

Developed by **Jadan Tech Solutions Nig Ltd**.

## Run it

Either open `index.html` in a browser, or run:

```bash
npm start
```

Then open http://localhost:3000.

## Sign in

- Email: `admin@jadanpay.app`
- Password: `admin123` (Super admin)

Change the password on **My profile** before using the dashboard with real data.

## Project structure

```
jadanpay-admin/
├── index.html      The whole dashboard (markup, CSS and JavaScript)
├── package.json    `npm start` dev server, no dependencies
├── .gitignore
└── README.md
```

## What it covers

- **Overview:** customers, volume, profit, wallet float, success rate, open tickets, 7-day chart.
- **Customers:** search and filters, credit or debit wallet, tier, suspend or activate, reset PIN, send alert.
- **Transactions:** filters, search, CSV export, refund to wallet.
- **Plans & bills:** data, cable TV, electricity, internet and other bills, each with its own fields. CSV import and export.
- **Services & pricing**, **network health**, **support inbox**, **announcements**, **referrals**, **reports**, **audit log**.
- **Integrations:** VTU provider, payment gateway, SMTP. Secret keys go to the backend and are never stored in the browser.
- **Brand:** name, tagline, colours, logo, footer, JSON export.
- **Staff, roles and permissions:** staff accounts with hashed passwords, custom roles, action checks, collapsible menu.
- **My profile**, **settings**, backups and data reset.

## Where the code lives (index.html)

Search for these names:
- `seed()`, `defaultCatalog()`, `defaultRoles()`: sample data
- `load()`, `save()`, `log()`: storage and audit
- `view…()` functions (for example `viewCatalog`, `viewStaff`): each page
- `ACT_PERM`, `VIEW_PERM`, `can()`: permissions
- `act()`: button actions
- `doLogin()`, `hashP()`: sign-in
- `render()`: redraws the screen
- The change and click handlers at the bottom: form fields and buttons

## Before going live

This is a front-end only. Data lives in the browser's local storage, not on a server. Accounts, staff and roles exist only on the computer where they were created.

Before real use, build a backend that:
- Stores customers, staff, roles, transactions and the catalog on a server
- Checks every permission and password on the server, with rate limits
- Keeps provider and payment secret keys on the server
- Records audit logs server-side

## Next steps for development

1. Split `index.html` into `css/admin.css` and `js/admin.js` once the file gets hard to navigate.
2. Connect the backend API, starting with staff sign-in and the catalog.
3. Add automated tests for permission checks, the catalog readiness rules and password rules.
4. Choose a license before publishing the repository.

---
© Jadan Tech Solutions Nig Ltd. All rights reserved.
