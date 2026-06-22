# Domain Setup Guide

## GoDaddy DNS Configuration

### Step 1: Add A Records for GitHub Pages

In your GoDaddy DNS settings for `methanemitigationpartners.com`, add these **A records**:

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | @ | 185.199.108.153 | 600 |
| A | @ | 185.199.109.153 | 600 |
| A | @ | 185.199.110.153 | 600 |
| A | @ | 185.199.111.153 | 600 |

### Step 2: Add CNAME Record for www

| Type | Name | Value | TTL |
|------|------|-------|-----|
| CNAME | www | leviathantx.github.io | 600 |

### Step 3: Configure GitHub Pages Custom Domain

1. Go to https://github.com/LeviathanTX/MMP/settings/pages
2. Under "Custom domain", enter: `methanemitigationpartners.com`
3. Click "Save"
4. Wait 10-15 minutes for DNS propagation
5. Check "Enforce HTTPS" once SSL certificate is issued (automatic)

### Step 4: Verify Setup

After 15-30 minutes, test:
- http://methanemitigationpartners.com (should redirect to https)
- https://methanemitigationpartners.com (should load site)
- https://www.methanemitigationpartners.com (should redirect to non-www)

## Optional: Email Setup

If you want email at your domain (e.g., `contact@methanemitigationpartners.com`):

### Option 1: Google Workspace ($6/user/month)
- Professional email
- Google Calendar, Drive, Docs
- Best for business

### Option 2: Zoho Mail (Free tier available)
- Up to 5 users free
- 5GB storage per user
- Good for startups

### Option 3: Forward to Gmail (Free)
1. In GoDaddy, set up email forwarding
2. Forward `contact@methanemitigationpartners.com` to your Gmail
3. Update privacy.html with the real email address

## Files Already Updated

✅ All URLs in the site now point to `methanemitigationpartners.com`:
- index.html (canonical, Open Graph, Twitter tags)
- privacy.html (canonical URL)
- sitemap.xml
- robots.txt

No code changes needed after domain setup!

## Troubleshooting

**Domain not loading after 30 minutes?**
- Check DNS propagation: https://www.whatsmydns.net/
- Verify A records are correct (all 4 IP addresses)
- Clear browser cache

**SSL certificate not working?**
- Wait 24 hours for GitHub to issue certificate
- Make sure "Enforce HTTPS" is enabled in GitHub Pages settings
- Check that DNS is fully propagated

**www not redirecting?**
- Verify CNAME record: `www` → `leviathantx.github.io`
- Wait for DNS propagation (up to 48 hours)
