# Rokda website

A static site for the Rokda app: home page, privacy policy and a 404 page. Plain HTML and CSS, no build step.

| File | What it is |
|---|---|
| `index.html` | Home page (use as the **app home page** URL) |
| `privacy.html` | Privacy policy (use as the **privacy policy** URL) |
| `terms.html` | Terms of service (use as the **terms of service** URL) |
| `404.html` | Shown by GitHub Pages for a missing page |
| `styles.css` | All styles, light and dark |
| `logo.svg`, `icon.png` | Logo and app icon |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Before you publish

1. Replace `your-email@example.com` in `index.html` and `privacy.html` with your support email (the same one you use in Play Console and Google Cloud).
2. When the app is live, change the "Coming soon" button in `index.html` to link to `https://play.google.com/store/apps/details?id=com.rokda.app` (the comment above it shows how).

## Publish on GitHub Pages

The best choice is a repository named **`<your-github-username>.github.io`**, for example `test-name.github.io`. The site is then at the root:

- Home page: `https://test-name.github.io/`
- Privacy policy: `https://test-name.github.io/privacy.html`
- Terms of service: `https://test-name.github.io/terms.html`

Google's sign-in consent screen asks you to prove you own the domain of these pages, and a site at the root is the one you can verify with Google Search Console.

```bash
cd D:\Tools\rokda_web
git init
git add .
git commit -m "Rokda website"
git branch -M main

git push -u origin main
```

Then on GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main, folder: / (root) → Save.** The site is live in a minute or two.

(A repository with any other name, such as `rokda`, also works, at `https://test-name.github.io/rokda/`, but that address is harder to verify for Google.)

## Prove you own the site (for the Google consent screen)

1. Open [Google Search Console](https://search.google.com/search-console) → **Add property → URL prefix** → `https://test-name.github.io/`.
2. Choose **HTML tag**, copy the `content="…"` code.
3. In `index.html`, uncomment the `google-site-verification` line and paste the code. Commit and push, then click **Verify**.
4. In Google Cloud → Google Auth Platform → Branding, add `test-name.github.io` under **Authorized domains**, and set:
   - Application home page: `https://test-name.github.io/`
   - Application privacy policy link: `https://test-name.github.io/privacy.html`
   - Application terms of service link: `https://test-name.github.io/terms.html`

Use the same privacy policy URL in Play Console → **Policy and programs → App content → Privacy policy**.
