# LA Global Website — Launch Checklist

This folder is the complete site. Upload everything in it to the root of your GitHub repo and the site will work as-is — but three things need to be connected before it's truly "live":

## 1. Deploy on GitHub Pages
- Push these files to the root of your repo (e.g. `laglobal/laglobal.io` or similar).
- In the repo: **Settings → Pages → Source → Deploy from branch → main → / (root)**.
- A `CNAME` file is already included, pointing at `laglobal.io`. If you're using a different domain, edit that file.

## 2. Point your domain at GitHub Pages
At your domain registrar (wherever laglobal.io is registered), add these DNS records:
- **A records** for the root domain (`laglobal.io`) pointing to GitHub's IPs:
  `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- **CNAME record** for `www` pointing to `<your-github-username>.github.io`
- In GitHub Pages settings, check "Enforce HTTPS" once DNS propagates (can take a few hours).

## 3. Connect the contact form
The form on `contact.html` posts to Formspree but isn't connected yet:
- Create a free account at [formspree.io](https://formspree.io), create a new form.
- Copy your endpoint (looks like `https://formspree.io/f/abcd1234`).
- In `contact.html`, find `action="https://formspree.io/f/YOUR_FORM_ID"` and replace `YOUR_FORM_ID` with your real ID.
- Until this is done, the form will show a "not connected yet" message instead of sending.

## Optional, but recommended before sharing the site publicly
- **Real email**: `hello@laglobal.io` is used throughout (contact page, footers, legal pages) — swap for your real inbox with find-and-replace across all `.html` files if different.
- **Legal review**: `privacy-policy.html` and `terms.html` are clearly marked as placeholder templates — have a lawyer review before relying on them.
- **Client portal**: `client-portal.html` is a UI shell with no live backend. See the HTML comment inside that file for three integration paths (a dedicated portal tool, an auth provider, or a custom backend) — pick one when you're ready to make it functional, or remove the nav/footer links to it until then.
- **Leadership bios & testimonials**: both currently use clearly-labeled placeholder content (no invented names or fabricated quotes) — replace with real bios/quotes on the About and Insights pages when available.

## Nothing else is required
Every internal link, the favicon, the stylesheet, and the script file are all already wired correctly and tested. No build step, no dependencies to install — it's a static site that works by being uploaded as-is.
