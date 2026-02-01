# Jorge Arauz - Portfolio

This portfolio website is built using [Docusaurus](https://docusaurus.io/), a modern static site generator.

## 🚀 Quick Start

### Installation

```bash
npm install
```

### Local Development

```bash
npm start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

### Build

```bash
npm run build
```

This command generates static content into the `build` directory.

## 📦 Deployment to Cloudflare Pages

### Cloudflare Pages Settings (IMPORTANT)

When configuring your Cloudflare Pages project, use these **exact settings**:

- **Framework preset:** `None` (or `Docusaurus`)
- **Build command:** `npm run build`
- **Build output directory:** `build`
- **Root directory:** `/` (leave empty)
- **Environment variables:** None needed
- **Deploy command:** **LEAVE EMPTY** (Do NOT use `npx wrangler deploy`)

> [!WARNING]
> Do NOT add a custom deploy command like `npx wrangler deploy`. Cloudflare Pages automatically handles deployment after the build completes. The `wrangler.jsonc` file is included for compatibility but Pages will use the build directory directly.

### Automatic Deployment (Recommended)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Update portfolio"
   git push origin main
   ```

2. **Connect to Cloudflare Pages** (First time only)
   - Go to [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - Navigate to **Workers & Pages** → **Create application** → **Pages** → **Connect to Git**
   - Select your GitHub repository
   - Configure build settings as shown above
   - Click **Save and Deploy**

3. **Automatic deployments**
   - Every push to `main` branch will trigger a new deployment automatically

### Manual Deployment (Alternative)

If you prefer manual deployments using Wrangler CLI:

```bash
# Build the site
npm run build

# Install Wrangler (if not installed)
npm install -g wrangler

# Login to Cloudflare (first time only)
wrangler login

# Deploy (wrangler.jsonc configures the build directory)
npx wrangler pages deploy
```

## 📝 Content Structure

- **`/docs/projects/`** - Individual project pages
- **`/src/pages/resume.md`** - Resume/CV page
- **`/blog/`** - Blog posts (optional)
- **`/static/img/`** - Images and assets
- **`docusaurus.config.js`** - Site configuration

## 🛠️ Customization

Edit `docusaurus.config.js` to update:
- Site title and tagline
- Navigation links
- Footer content
- GitHub/LinkedIn URLs

## 📧 Contact

**Jorge Arauz**  
Email: jorgegato1998@gmail.com  
GitHub: [@JArauzB](https://github.com/JArauzB)  
LinkedIn: [jorge-arauz](https://nl.linkedin.com/in/jorge-arauz-0aa988191)
