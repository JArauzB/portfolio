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

### Option 1: Automatic Deployment (Recommended)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Update portfolio"
   git push origin main
   ```

2. **Connect to Cloudflare Pages**
   - Go to [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - Navigate to **Workers & Pages** → **Create application** → **Pages**
   - Connect your GitHub repository
   - Configure build settings:
     - **Build command:** `npm run build`
     - **Build output directory:** `build`
     - **Node version:** `18` or higher

3. **Save and Deploy**
   - Cloudflare will automatically build and deploy your site
   - Every push to `main` branch will trigger a new deployment

### Option 2: Manual Deployment

```bash
# Build the site
npm run build

# Install Wrangler (Cloudflare CLI)
npm install -g wrangler

# Login to Cloudflare
wrangler login

# Deploy
wrangler pages deploy build --project-name=portfolio
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
