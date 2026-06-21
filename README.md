# MistakeLab Legal Pages

Static Terms, Privacy Policy, and Impressum for [mistakelab.app](https://mistakelab.app), hosted on GitHub Pages.

## URLs for App Store & Google Play

| Document | URL |
|----------|-----|
| Privacy Policy | https://mistakelab.app/privacy |
| Terms & Conditions | https://mistakelab.app/terms |
| Impressum | https://mistakelab.app/terms#impressum |

## Deploy to GitHub Pages

These files belong at the **root** of the [MistakeLab-legal](https://github.com/) repository (not in a subfolder).

### 1. Push to GitHub

From this folder:

```bash
cd legal
git init
git remote add origin git@github.com:ozgo0/MistakeLab-legal.git
git add .
git commit -m "Add legal pages for GitHub Pages"
git branch -M main
git push -u origin main
```

If the repo already exists with content, clone it, copy these files into the repo root, then commit and push.

### 2. Enable GitHub Pages

In the **MistakeLab-legal** repo on GitHub:

1. **Settings → Pages**
2. **Build and deployment → Source:** Deploy from a branch
3. **Branch:** `main` / **Folder:** `/ (root)`
4. **Custom domain:** `mistakelab.app`
5. Enable **Enforce HTTPS** once DNS has propagated

The `CNAME` file in this folder tells GitHub to use your custom domain.

### 3. Configure DNS

At your domain registrar (where you bought `mistakelab.app`), add:

**Option A — Apex domain (recommended for `mistakelab.app`):**

| Type | Name | Value |
|------|------|-------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |

**Option B — CNAME (if your registrar supports CNAME flattening on apex):**

| Type | Name | Value |
|------|------|-------|
| CNAME | `@` | `ozgo0.github.io` |

Also add the `www` redirect if you want it:

| Type | Name | Value |
|------|------|-------|
| CNAME | `www` | `ozgo0.github.io` |

Replace `ozgo0` with your GitHub username if different.

DNS can take up to 24–48 hours to propagate. GitHub will show a green checkmark under **Settings → Pages** when the domain is verified.

### 4. Verify

After deployment, confirm these load in a browser:

- https://mistakelab.app/
- https://mistakelab.app/privacy
- https://mistakelab.app/terms

Use these exact URLs in App Store Connect and Google Play Console.

## File structure

```
.
├── CNAME              # Custom domain (mistakelab.app)
├── .nojekyll          # Disable Jekyll processing
├── index.html         # Landing page with links
├── privacy/
│   └── index.html     # Privacy Policy
├── terms/
│   └── index.html     # Terms & Conditions + Impressum
└── README.md
```

## Updating content

Edit the HTML files directly, commit, and push. Changes go live within a minute or two after GitHub Pages rebuilds.
