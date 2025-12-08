# Quick Setup Guide for Custom Domain

## When You're Ready to Add Your Custom Domain

### Quick Steps:
1. **Buy your domain** from a registrar (Ionos, Namecheap, Google Domains, etc.)

2. **Create CNAME file:**
   ```bash
   # Rename the template file
   mv CNAME.template CNAME
   
   # Edit CNAME and add your domain (just the domain, no https://)
   echo "yourdomain.com" > CNAME
   
   # Commit and push
   git add CNAME
   git commit -m "Add custom domain"
   git push
   ```

3. **Configure DNS** at your domain registrar:
   
   **For apex domain (yourdomain.com):**
   - Add A records pointing to:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153
   
   **For subdomain (www.yourdomain.com):**
   - Add CNAME record: `www` → `glimmercharger.github.io`

4. **Configure in GitHub:**
   - Go to Settings → Pages
   - Enter your custom domain
   - Enable "Enforce HTTPS"

5. **Wait:** DNS propagation can take 24-48 hours

## Important Notes:
- Your site will continue working at `glimmercharger.github.io` during the transition
- Don't create the CNAME file until you've purchased your domain
- GitHub will automatically provision an SSL certificate for HTTPS

## Example Domains:
- `willk.com` (if available)
- `willkitch.com` (if available)
- `glimmercharger.com` (if available)
- Or any subdomain like `www.yourdomain.com`
