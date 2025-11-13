# Setup Instructions for GitHub Pages

Follow these steps to deploy this website to GitHub Pages.

## Step 1: Create GitHub Repository

1. Go to [GitHub](https://github.com) and log in
2. Click the **+** icon in the top right → **New repository**
3. Repository settings:
   - **Name**: `pct-map-website` (or any name you prefer)
   - **Description**: "Interactive map of Dori's PCT adventure"
   - **Visibility**: Public (required for free GitHub Pages)
   - **DO NOT** initialize with README (we already have one)
4. Click **Create repository**

## Step 2: Push Code to GitHub

In your terminal, from the `pct-map-website` directory:

```bash
# Initialize git repository
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit - Dori's PCT Adventure map"

# Add your GitHub repository as remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/pct-map-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Click **Pages** (left sidebar)
4. Under "Source":
   - Branch: Select **main**
   - Folder: Select **/ (root)**
5. Click **Save**

## Step 4: Wait for Deployment

- GitHub will build and deploy your site (takes 1-2 minutes)
- You'll see a message: "Your site is live at https://YOUR_USERNAME.github.io/pct-map-website/"
- Click the link to view your live map!

## Step 5: Update the README

Edit `README.md` and replace `YOUR_USERNAME` with your actual GitHub username in the live map link.

## Updating the Map Data

When you have new camping location data:

1. In the main `GarminMessages` project, run:
   ```bash
   ./generate_map_data.sh
   ./deploy_to_website.sh
   ```

2. In the `pct-map-website` directory:
   ```bash
   git add .
   git commit -m "Update camping locations - Day X"
   git push
   ```

3. GitHub Pages will automatically update (takes 1-2 minutes)

## Custom Domain (Optional)

If you want to use a custom domain like `pct.yourdomain.com`:

1. Buy a domain from a registrar (Namecheap, Google Domains, etc.)
2. In your repository Settings → Pages → Custom domain
3. Enter your domain and click Save
4. Configure DNS at your registrar:
   - Add a CNAME record pointing to `YOUR_USERNAME.github.io`
5. Wait for DNS propagation (can take up to 24 hours)

## Troubleshooting

**Site not loading?**
- Check Settings → Pages to see deployment status
- Make sure the repository is Public
- Wait a few minutes after pushing changes

**Map not showing?**
- Open browser console (F12) to check for errors
- Verify `pct_trail.json` and `daily_locations.json` are in the repository
- Check that file paths in `index.html` are correct (no `webapp/` prefix)

**Need help?**
- Check [GitHub Pages documentation](https://docs.github.com/en/pages)
- Verify all files are committed: `git status`

