# Cleveland African Mart

Landing page and e-commerce site for Cleveland African Mart.

## Project Overview

A modern, responsive website showcasing African food products with:
- Landing page (3 design options: Night Market, Fresh, Terra)
- Product categories (beverages, spices, produce, etc.)
- Shop & product browse
- About & contact pages
- Mobile-responsive design

## Deploy Configuration (configured by /setup-deploy)
- Platform: Cloudflare Pages
- Production URL: https://clevelandafricanmart.com (update when domain is set)
- Deploy workflow: GitHub → Cloudflare Pages (auto-deploy on push to main)
- Deploy status command: `wrangler pages project list` or HTTP health check
- Merge method: squash
- Project type: static website
- Post-deploy health check: GET https://clevelandafricanmart.com → 200 OK

### Deployment Steps

1. **Install Wrangler** (if not already installed):
   ```bash
   npm install -g wrangler
   ```

2. **Authenticate with Cloudflare**:
   ```bash
   wrangler login
   ```

3. **Create a Cloudflare Pages project**:
   ```bash
   wrangler pages project create cleveland-african-mart
   ```

4. **Connect GitHub repo** (from Cloudflare dashboard):
   - Go to https://dash.cloudflare.com
   - Navigate to Pages
   - Select "Connect to Git"
   - Authorize GitHub and select this repository
   - Set build command: (leave empty)
   - Set build output directory: (leave as root or `.`)
   - Save and deploy

5. **Deploy locally** (optional, for testing):
   ```bash
   npm install
   wrangler pages deploy
   ```

### Custom deploy hooks
- Pre-merge: none
- Deploy trigger: automatic on push to main (via GitHub integration)
- Deploy status: poll production URL
- Health check: GET / → 200 OK with index.html content

## Next Steps

After deployment:
- Update the production URL above once domain is configured
- Set up custom domain in Cloudflare Pages settings
- Configure analytics (optional)
- Set up email forwarding or contact form backend
