# gh-deployment-workflow

A minimal CI/CD demonstration project that automatically deploys a static website to **GitHub Pages** using **GitHub Actions** — triggered only when `index.html` changes.

---

## 🚀 Live Site

> `hhttps://github.com/Tessie27/gh-deployment-workflow`

---

## 📁 Project Structure

```
gh-deployment-workflow/
├── index.html                  # The static website
├── README.md                   # This file
└── .github/
    └── workflows/
        └── deploy.yml          # GitHub Actions CI/CD workflow
```

---

## ⚙️ How It Works

The GitHub Actions workflow in `.github/workflows/deploy.yml` is configured to:

1. **Trigger only on `index.html` changes** pushed to the `main` branch  
   (using the `paths` filter — other file changes are ignored).
2. **Check out** the repository code.
3. **Configure** GitHub Pages via the official action.
4. **Upload** the site files as a Pages artifact.
5. **Deploy** the artifact to GitHub Pages.

```yaml
on:
  push:
    branches: [main]
    paths:
      - index.html   # ← Only runs when this file changes
```

---

## 🛠️ Setup Instructions

### 1. Fork or clone this repository

```bash
git clone https://github.com/<your-username>/gh-deployment-workflow.git
cd gh-deployment-workflow
```

### 2. Enable GitHub Pages in the repository settings

- Go to **Settings → Pages**
- Under **Source**, select **GitHub Actions**

### 3. Push a change to `index.html`

```bash
# Edit index.html, then:
git add index.html
git commit -m "Update site content"
git push origin main
```

The workflow will trigger automatically and deploy your changes within seconds.

---

## 🔄 CI/CD Pipeline Overview

```
Push to main (index.html changed)
        │
        ▼
  GitHub Actions triggered
        │
        ▼
  Checkout → Configure Pages → Upload Artifact → Deploy
        │
        ▼
  Live at https://<username>.github.io/gh-deployment-workflow/
```

---

## 📚 References

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [actions/deploy-pages](https://github.com/actions/deploy-pages)
