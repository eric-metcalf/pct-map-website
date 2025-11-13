# Deployment Summary

## What We've Created

You now have a **two-repository setup**:

### 1. **GarminMessages** (Private - Data Processing)
- Location: Current repository
- Purpose: Process Garmin inReach messages and generate map data
- Contains: Scala code, message dumps, GPX files
- **Keep this private** - contains personal message data

### 2. **pct-map-website** (Public - Website)
- Location: `pct-map-website/` folder
- Purpose: Public website hosted on GitHub Pages
- Contains: HTML, JSON data files (no personal messages, just GPS points)
- **Make this public** - safe to share

## Files in Website Repository

```
pct-map-website/
├── index.html              # Main web application
├── pct_trail.json          # PCT trail coordinates (4.5 MB)
├── daily_locations.json    # Daily camping locations (41 KB)
├── README.md               # Website documentation
├── SETUP.md                # GitHub Pages setup instructions
└── .gitignore              # Git ignore rules
```

## Workflow

### Initial Setup (One Time)

1. **Create GitHub repository for website**:
   ```bash
   cd pct-map-website
   git init
   git add .
   git commit -m "Initial commit - Dori's PCT Adventure"
   git remote add origin https://github.com/YOUR_USERNAME/pct-map-website.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**:
   - Go to repository Settings → Pages
   - Source: main branch, / (root) folder
   - Save

3. **Wait 1-2 minutes** for deployment

4. **Visit your live site**:
   - https://YOUR_USERNAME.github.io/pct-map-website/

### Regular Updates (When You Have New Data)

From the `GarminMessages` repository:

```bash
# 1. Generate latest data from messages
./generate_map_data.sh

# 2. Copy to website repository
./deploy_to_website.sh

# 3. Commit and push website updates
cd pct-map-website
git add .
git commit -m "Update camping locations - Day X"
git push

# 4. Wait 1-2 minutes for GitHub Pages to update
```

## What Gets Published

### ✅ Safe to Publish (in website repo)
- GPS coordinates (latitude/longitude)
- Day numbers
- Dates
- Altitude data
- Trail route

### ❌ NOT Published (stays in GarminMessages repo)
- Full message text (only GPS data is extracted)
- Phone numbers
- Raw Garmin message dumps
- Scala source code
- Personal information

## Privacy Notes

The `daily_locations.json` file contains:
- Day number
- Date/time
- GPS coordinates
- Altitude
- Message text (your daily check-in messages)

**Important**: If your daily messages contain sensitive information, you may want to:
1. Filter out the message text in `CsvToJsonConverter.scala`
2. Only publish GPS coordinates and day numbers
3. Keep messages private

## Customization

### Change Map Style
Edit `index.html` line ~171 to use different map tiles:
- Current: Stadia Maps Outdoors
- Alternatives listed in code comments

### Update Title/Branding
Edit `index.html`:
- Line 6: Browser tab title
- Line 132: Page header
- Lines 138-144: Info panel content

### Modify Trail Colors
Edit `index.html` line ~186:
- Trail color: `color: '#e74c3c'` (currently red)
- Camping markers: `fillColor: '#27ae60'` (currently green)

## Troubleshooting

**Website not updating?**
- Check GitHub Actions tab for deployment status
- Clear browser cache (Cmd+Shift+R)
- Verify files were pushed: `git log`

**Map not loading?**
- Open browser console (F12) to check errors
- Verify JSON files are valid
- Check file sizes aren't too large (GitHub has 100MB limit)

**Trail not showing?**
- Ensure `pct_trail.json` is committed
- Check browser console for fetch errors
- Verify file path in `index.html` is correct

## Next Steps

1. Follow `SETUP.md` to create GitHub repository
2. Push code and enable GitHub Pages
3. Share your live map URL!
4. Update regularly as you add new camping locations

## Support

- GitHub Pages Docs: https://docs.github.com/en/pages
- Leaflet.js Docs: https://leafletjs.com/
- Stadia Maps: https://stadiamaps.com/

Enjoy sharing Dori's PCT adventure! 🥾🏔️

