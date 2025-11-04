# Cloudflare Pages Deployment Guide

This guide walks you through deploying your bilingual pentester portfolio website to Cloudflare Pages using GitHub integration.

## Prerequisites
- GitHub account with a public repository named "cloudflare"
- Cloudflare account
- Domain `olyhome.site` (preferably managed by Cloudflare)
- Local Git installation

---

## Phase 1: Prepare Local Repository

### Step 1: Navigate to Project Directory
```bash
cd /home/f4blox/Desktop/Gemini/opencode/WEBSITE_PROJECT/
```

### Step 2: Initialize Git Repository
```bash
git init
```

### Step 3: Add All Files
```bash
git add .
```

### Step 4: Create Initial Commit
```bash
git commit -m "Initial commit: Bilingual pentester portfolio website with blog"
```

### Step 5: Add GitHub Remote
Replace `[username]` with your actual GitHub username:
```bash
git remote add origin https://github.com/[username]/cloudflare.git
```

### Step 6: Push to GitHub
```bash
git push -u origin main
```

**Expected Result:** Your website files are now on GitHub in the "cloudflare" repository.

---

## Phase 2: Connect Cloudflare Pages

### Step 1: Access Cloudflare Dashboard
1. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Select your account
3. Click on "Pages" in the sidebar

### Step 2: Create New Pages Project
1. Click "Create a project"
2. Choose "Connect to Git"
3. Select your GitHub account
4. Find and select the "cloudflare" repository
5. Click "Begin setup"

### Step 3: Configure Build Settings
Set the following exactly:

| Setting | Value |
|---------|-------|
| **Framework preset** | None |
| **Build command** | (leave empty) |
| **Build output directory** | `html` |
| **Root directory** | `/` |

Click "Save and Deploy"

**Note:** Since this is a static HTML site, no build command is needed.

---

## Phase 3: Configure Custom Domain

### Step 1: Add Custom Domain
1. In your Pages project, go to "Custom domains" tab
2. Click "Set up a custom domain"
3. Enter: `olyhome.site`
4. Click "Continue"

### Step 2: DNS Configuration
Cloudflare will provide DNS instructions. Follow them exactly:

#### For Apex Domain (olyhome.site)
If your domain is managed by Cloudflare:
- Cloudflare will automatically handle the DNS configuration
- No additional steps needed

If your domain is NOT managed by Cloudflare:
- Add these A records at your DNS provider:
  ```
  Type: A
  Name: @
  Value: [Cloudflare Pages IP addresses - check dashboard]
  ```
- Or follow Cloudflare's specific instructions

#### For Subdomains (optional)
If you want www.olyhome.site:
```
Type: CNAME
Name: www
Value: [your-pages-url].pages.dev
```

### Step 3: SSL/TLS Settings
1. Go to SSL/TLS > Overview in Cloudflare dashboard
2. Ensure SSL is set to "Full (strict)" or higher
3. Cloudflare Pages provides automatic SSL certificates

### Step 4: Verify DNS Propagation
- Use tools like [DNS Checker](https://dnschecker.org) to verify `olyhome.site` points to Cloudflare
- DNS changes can take 24-48 hours to propagate globally

---

## Phase 4: Test and Verify

### Step 1: Check Deployment Status
1. In Cloudflare Pages dashboard, check the deployment status
2. Look for green "Success" indicator
3. If failed, check build logs for errors

### Step 2: Test the Live Site
1. Visit `https://olyhome.site`
2. Test both English (`/index.html`) and French (`/index-fr.html`) versions
3. Navigate through the blog categories
4. Check responsive design on mobile

### Step 3: Test Key Features
- Language toggle functionality
- Project filtering
- Blog navigation
- Contact form (if implemented)
- All image assets load correctly

### Step 4: Verify SEO and Performance
- Check page load times
- Verify meta tags and Open Graph images
- Test on multiple browsers and devices

---

## Automation Setup

### How Auto-Deployment Works
- Every `git push` to the `main` branch triggers a new build
- Builds typically complete in 1-2 minutes
- Previous deployments remain accessible via deployment history

### Monitoring Builds
1. In Cloudflare Pages > your project > Deployments tab
2. Click on any deployment to view logs
3. Green = success, Red = failed

### Rollback if Needed
1. Go to Deployments tab
2. Find a successful previous deployment
3. Click "Rollback to this deployment"

### Preview Deployments
- Push to branches (not main) to create preview URLs
- Useful for testing changes before merging
- Preview URLs: `https://[branch-name].[project-name].pages.dev`

---

## Domain Configuration Details

### DNS Records Needed
For `olyhome.site` (apex domain):
- Cloudflare manages this automatically if domain is on Cloudflare
- Otherwise, add A records pointing to Cloudflare's edge network IPs

### SSL Certificate
- Automatic via Cloudflare
- Always-On SSL enabled by default
- Supports HTTP/2 and HTTP/3

### Subdomain Options
If you want to organize content:
- `blog.olyhome.site` - point to `/html/blog/`
- `en.olyhome.site` - point to `/html/index.html`
- `fr.olyhome.site` - point to `/html/index-fr.html`

---

## Troubleshooting Guide

### Build Failures
**Symptom:** Red deployment status
**Solutions:**
1. Check build logs for specific errors
2. Ensure all files are committed and pushed
3. Verify file paths are correct (case-sensitive)
4. Check for broken links or missing assets

### 404 Errors
**Symptom:** Pages not found
**Solutions:**
1. Verify build output directory is set to `html`
2. Check that `index.html` exists in `html/` folder
3. Ensure all internal links use correct relative paths
4. Test locally with a web server first

### DNS Not Resolving
**Symptom:** Site not accessible
**Solutions:**
1. Wait 24-48 hours for DNS propagation
2. Verify DNS records are correct
3. Check domain registrar settings
4. Use `dig olyhome.site` to check DNS

### SSL Certificate Issues
**Symptom:** HTTPS not working
**Solutions:**
1. Ensure domain is properly configured in Cloudflare
2. Check SSL/TLS settings are set correctly
3. Wait for certificate provisioning (can take up to 24 hours)
4. Clear browser cache and try incognito mode

### Slow Loading
**Symptom:** Site loads slowly
**Solutions:**
1. Optimize images (compress, use WebP format)
2. Enable Cloudflare's caching and optimization features
3. Minimize CSS/JS files
4. Use a CDN for external resources if needed

### Content Issues
**Symptom:** Broken images or styles
**Solutions:**
1. Verify all asset paths are updated correctly
2. Check that `css/`, `js/`, `assets/` folders are in `html/`
3. Ensure relative paths match the new structure
4. Test locally before pushing

### Git Issues
**Symptom:** Push fails
**Solutions:**
1. Ensure you're pushing to the correct remote
2. Check repository permissions
3. Resolve any merge conflicts
4. Use `git status` to check repository state

---

## Post-Deployment Checklist

- [ ] Site loads at `https://olyhome.site`
- [ ] Both English and French versions work
- [ ] All blog articles are accessible
- [ ] Images and assets load correctly
- [ ] Mobile responsive design works
- [ ] SSL certificate is valid
- [ ] DNS resolves correctly worldwide
- [ ] Auto-deployment triggers on push
- [ ] Contact form functions (if applicable)

---

## Maintenance

### Updating Content
1. Make changes locally
2. Test thoroughly
3. Commit and push to `main` branch
4. Cloudflare will auto-deploy

### Adding New Features
1. Develop locally
2. Test on multiple devices/browsers
3. Update this documentation if needed
4. Deploy via Git push

### Monitoring Performance
- Use Cloudflare Analytics for traffic insights
- Monitor build times and success rates
- Set up alerts for failed deployments

---

## Support Resources

- [Cloudflare Pages Documentation](https://developers.cloudflare.com/pages/)
- [Cloudflare DNS Guide](https://developers.cloudflare.com/dns/)
- [GitHub Pages vs Cloudflare Pages](https://blog.cloudflare.com/cloudflare-pages-vs-github-pages/)
- [SSL/TLS Best Practices](https://developers.cloudflare.com/ssl/)

---

**Need Help?** Check the troubleshooting section above, then reach out to Cloudflare support or check their community forums.