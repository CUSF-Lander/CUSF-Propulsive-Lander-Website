# CUSF Propulsive Lander Team Website

Official website for the Cambridge University Spaceflight (CUSF) Propulsive Lander Team, showcasing our journey to develop a reusable liquid-fuelled hopper rocket for the Collegiate Propulsive Lander Challenge (CPLC).

## Hosting on GitHub Pages

### Initial Setup

1. **Create a GitHub Repository**
   - Go to [GitHub](https://github.com) and sign in
   - Click the "+" icon in the top right and select "New repository"
   - Name your repository (e.g., `cusf-lander-website`)
   - Choose "Public" (required for free GitHub Pages)
   - Do NOT initialize with README, .gitignore, or license (we already have files)
   - Click "Create repository"

2. **Initialize Git and Push Your Code**

   Open your terminal in this project directory and run:

   ```bash
   # Initialize git repository
   git init

   # Add all files
   git add .

   # Create first commit
   git commit -m "Initial commit: CUSF Propulsive Lander website"

   # Add your GitHub repository as remote (replace USERNAME and REPO_NAME)
   git remote add origin https://github.com/USERNAME/REPO_NAME.git

   # Push to GitHub
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Click "Settings" tab
   - Click "Pages" in the left sidebar
   - Under "Source", select "Deploy from a branch"
   - Under "Branch", select "main" and "/ (root)"
   - Click "Save"
   - Your site will be published at: `https://USERNAME.github.io/REPO_NAME/`

4. **Wait for Deployment**
   - GitHub Pages typically takes 1-2 minutes to build and deploy
   - You'll see a green checkmark when it's ready
   - Visit your site at the URL provided

## Using a Custom Domain

### Option 1: Custom Domain (e.g., cusfhopper.com)

1. **Purchase a Domain**
   - Buy a domain from a registrar (Namecheap, Google Domains, Cloudflare, etc.)

2. **Configure DNS Records**

   In your domain registrar's DNS settings, add these records:

   ```
   Type    Name    Value                     TTL
   A       @       185.199.108.153           3600
   A       @       185.199.109.153           3600
   A       @       185.199.110.153           3600
   A       @       185.199.111.153           3600
   CNAME   www     USERNAME.github.io        3600
   ```

   Replace `USERNAME` with your GitHub username.

3. **Configure GitHub Pages**
   - Go to your repository Settings → Pages
   - Under "Custom domain", enter your domain (e.g., `cusfhopper.com`)
   - Click "Save"
   - Check "Enforce HTTPS" (wait a few minutes for SSL certificate)

4. **Create CNAME File**

   Create a file named `CNAME` in your repository root with your domain:

   ```bash
   echo "cusfhopper.com" > CNAME
   git add CNAME
   git commit -m "Add custom domain"
   git push
   ```

### Option 2: Subdomain (e.g., lander.cusf.com)

If you already own a domain (like cusf.com):

1. **Configure DNS Records**

   In your domain's DNS settings:

   ```
   Type    Name      Value                     TTL
   CNAME   lander    USERNAME.github.io        3600
   ```

2. **Configure GitHub Pages**
   - Go to repository Settings → Pages
   - Enter your subdomain: `lander.cusf.com`
   - Click "Save" and enable HTTPS

3. **Create CNAME File**

   ```bash
   echo "lander.cusf.com" > CNAME
   git add CNAME
   git commit -m "Add custom subdomain"
   git push
   ```

### Option 3: GitHub Username Site (USERNAME.github.io)

For a simpler URL without a repository name:

1. **Create Special Repository**
   - Repository name MUST be: `USERNAME.github.io` (replace USERNAME with your actual GitHub username)
   - Example: If your username is `cuspaceflight`, name it `cuspaceflight.github.io`

2. **Push Your Code**
   - Follow the same git steps as above
   - Your site will be at: `https://USERNAME.github.io/` (no repository name in URL)

3. **For Custom Domain**
   - Follow the same custom domain steps above
   - DNS setup remains the same

## DNS Propagation

After configuring DNS:
- Changes can take 24-48 hours to fully propagate worldwide
- Usually works within 15 minutes to a few hours
- Use [DNS Checker](https://dnschecker.org) to verify propagation
- Be patient if your domain doesn't work immediately

## Troubleshooting

### Site Not Loading
- Wait a few minutes after enabling GitHub Pages
- Check Actions tab for deployment status
- Ensure `index.html` is in the root directory
- Clear browser cache or try incognito mode

### Custom Domain Not Working
- Verify DNS records are correct (use `dig yourdomain.com` or `nslookup`)
- Wait for DNS propagation (up to 48 hours)
- Ensure CNAME file contains only your domain name
- Check that "Enforce HTTPS" is enabled

### Images Not Loading
- Verify all image paths are correct: `static/filename.ext`
- Ensure the `static` folder was pushed to GitHub
- Check browser console (F12) for 404 errors
- File names are case-sensitive on GitHub Pages

### 404 Page Not Found
- Ensure your repository is public
- Check that GitHub Pages is enabled in Settings
- Verify the branch and folder settings are correct
- Make sure `index.html` exists in the selected location

## Making Updates

To update your website:

```bash
# Make your changes to index.html or other files

# Stage changes
git add .

# Commit with descriptive message
git commit -m "Update milestones section"

# Push to GitHub
git push

# GitHub Pages will automatically rebuild (takes 1-2 minutes)
```

## Project Structure

```
CUSF-Propulsive-Lander-Website/
├── index.html          # Main website file
├── static/             # Images and assets
│   ├── Lander Team Logo.png
│   ├── TVC-Drone-CAD-2025-11-16 at 01.23.02.jpeg
│   ├── engine-0-2.png
│   ├── engine-1.png
│   ├── engine-1-2.png
│   ├── engine-2.png
│   ├── SpaceX-Starhopper.jpg
│   ├── team-photo-IMG_8239 LQ JPG.jpg
│   ├── CUSF.svg
│   ├── CUSF.png
│   └── CUSF Poster-3.png
├── .nojekyll           # Tells GitHub not to use Jekyll
├── CNAME               # Custom domain configuration (create when needed)
└── README.md           # This file
```

## Technologies Used

- HTML5
- Tailwind CSS (via CDN)
- Google Fonts (Montserrat)
- Responsive design for mobile/tablet/desktop

## Credits

Website for the Cambridge University Spaceflight (CUSF) Propulsive Lander Team.

© 2025 Cambridge University Spaceflight. All rights reserved.

## Links

- [Main CUSF Website](https://www.cusf.co.uk/)
- [CUSF Instagram](https://www.instagram.com/cuspaceflight/)
- [Collegiate Propulsive Lander Challenge](https://cplc.space/)
