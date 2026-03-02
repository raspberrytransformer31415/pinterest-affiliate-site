# pinterest-affiliate-site

Minimal static site for Pinterest app setup + affiliate compliance pages.

## Files
- `index.html`
- `privacy.html`
- `affiliate-disclosure.html`

## 1) Authenticate GitHub CLI

```bash
gh auth login --web --git-protocol https
# verify
gh auth status
```

## 2) Create repo + push

Replace `<github-username>` before running.

```bash
cd /home/llmworker/.openclaw/workspace/pinterest-affiliate-site
git init
git add .
git commit -m "init affiliate site"
gh repo create <github-username>/pinterest-affiliate-site --public --source=. --remote=origin --push
```

## 3) Enable GitHub Pages

```bash
gh api \
  -X POST \
  repos/<github-username>/pinterest-affiliate-site/pages \
  -f source[branch]=main \
  -f source[path]=/
```

Your site URL will be:
`https://<github-username>.github.io/pinterest-affiliate-site/`

## 4) Pinterest Developer App fields

Use:
- Company website or App link:
  `https://<github-username>.github.io/pinterest-affiliate-site/`
- Link to privacy policy:
  `https://<github-username>.github.io/pinterest-affiliate-site/privacy.html`

## 5) Before publishing

- Replace `contact@example.com` in `privacy.html` with your real contact.
- Confirm affiliate wording in `affiliate-disclosure.html` matches your legal/compliance needs.
