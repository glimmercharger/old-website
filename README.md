# glimmercharger.github.io

My Personal Site is now online and working (Hosted on GitHub Pages!)
Link: [https://glimmercharger.github.io](https://glimmercharger.github.io/)

# Will K :)

---

## Custom Domain Setup Guide

This repository is configured to work with GitHub Pages and is ready for custom domain configuration when you purchase a domain.

### Current Status
- ✅ GitHub Pages is active and working at: https://glimmercharger.github.io
- 🔄 Ready for custom domain setup (pending domain purchase)

### How to Add a Custom Domain (When Ready)

#### Step 1: Purchase Your Domain
Buy a domain from a registrar like:
- [Ionos](https://www.ionos.com/) ✨
- [Namecheap](https://www.namecheap.com/)
- [Google Domains](https://domains.google/)
- [GoDaddy](https://www.godaddy.com/)
- [Cloudflare](https://www.cloudflare.com/products/registrar/)

#### Step 2: Create CNAME File
Create a file named `CNAME` (no extension) in the root of this repository with your domain:
```
yourdomain.com
```
Or for a subdomain:
```
www.yourdomain.com
```

**Note:** Commit and push this file to GitHub.

#### Step 3: Configure DNS Settings
Add DNS records at your domain registrar:

**Option A: Using an apex domain (yourdomain.com)**
Add these A records:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**Option B: Using a subdomain (www.yourdomain.com)**
Add a CNAME record:
```
CNAME: www -> glimmercharger.github.io
```

#### Step 4: Configure in GitHub
1. Go to your repository settings
2. Navigate to Pages section
3. Under "Custom domain", enter your domain
4. Check "Enforce HTTPS" (wait for SSL certificate provisioning)

#### Step 5: Wait for DNS Propagation
- DNS changes can take 24-48 hours to propagate
- Your site will continue working at glimmercharger.github.io during this time

### Testing Your Setup
Once configured, test your custom domain:
```bash
# Check DNS resolution
dig yourdomain.com

# Verify it points to GitHub Pages
nslookup yourdomain.com
```

### Ionos-Specific Instructions
If you're using Ionos as your domain registrar:
1. Log in to your Ionos account
2. Go to **Domains & SSL** → Select your domain
3. Click **DNS** settings
4. **For apex domain (yourdomain.com):**
   - Add 4 A Records with the GitHub IPs listed above
   - Set TTL to 3600 (or default)
5. **For subdomain (www.yourdomain.com):**
   - Add a CNAME record: `www` → `glimmercharger.github.io`
   - Set TTL to 3600 (or default)
6. Save changes and wait for propagation (usually 1-24 hours)

### Troubleshooting
- **Site not loading?** Check DNS propagation status at [whatsmydns.net](https://www.whatsmydns.net/)
- **Certificate errors?** Wait for GitHub to provision SSL (can take up to 24 hours)
- **404 errors?** Ensure CNAME file contains the correct domain

### Additional Resources
- [GitHub Pages Custom Domain Documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
