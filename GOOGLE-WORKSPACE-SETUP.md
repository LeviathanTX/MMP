# Google Workspace Email Setup for MMP

## Step 1: Sign Up for Google Workspace

1. Go to https://workspace.google.com/
2. Click "Get Started"
3. Choose plan:
   - **Business Starter** ($6/user/month) - Recommended for small team
   - **Business Standard** ($12/user/month) - If you need more storage/features
4. Enter business information:
   - Business name: `Methane Mitigation Partners`
   - Number of employees: (your choice)
   - Country: United States
5. Enter your details:
   - Name: Jeff Levine
   - Current email: leviathantx@gmail.com (for setup notifications)
6. Enter domain: `methanemitigationpartners.com`
   - Choose "Yes, I have one I can use"

## Step 2: Verify Domain Ownership

Google will ask you to verify you own the domain. Choose the **TXT record** method:

### In GoDaddy DNS:

1. Log into GoDaddy (https://dcc.godaddy.com)
2. Go to your domain: methanemitigationpartners.com
3. Click "DNS" or "Manage DNS"
4. Click "Add" to add a new record
5. Add this TXT record:
   ```
   Type: TXT
   Name: @ (or leave blank)
   Value: google-site-verification=XXXXXXXXXX (Google will give you this)
   TTL: 1 Hour (3600)
   ```
6. Click "Save"
7. Go back to Google Workspace and click "Verify"

**Note:** DNS changes can take 15 minutes to propagate. You may need to wait and retry.

## Step 3: Add MX Records for Email

Once domain is verified, Google will provide MX records. Add these to GoDaddy:

### In GoDaddy DNS:

**IMPORTANT:** Delete any existing MX records first!

Add these 5 MX records:

| Priority | Type | Name | Value | TTL |
|----------|------|------|-------|-----|
| 1 | MX | @ | ASPMX.L.GOOGLE.COM | 1 Hour |
| 5 | MX | @ | ALT1.ASPMX.L.GOOGLE.COM | 1 Hour |
| 5 | MX | @ | ALT2.ASPMX.L.GOOGLE.COM | 1 Hour |
| 10 | MX | @ | ALT3.ASPMX.L.GOOGLE.COM | 1 Hour |
| 10 | MX | @ | ALT4.ASPMX.L.GOOGLE.COM | 1 Hour |

**Note:** The "Name" field should be `@` or left blank (means root domain).

## Step 4: Create Email Accounts

Once MX records are set up (wait 15-30 minutes):

1. Go to Google Admin console (admin.google.com)
2. Click "Users"
3. Click "Add new user"
4. Create your primary email:
   - First name: Jeff
   - Last name: Levine
   - Primary email: `jeff@methanemitigationpartners.com` (or `contact@`, `info@`, etc.)
   - Create password
5. Click "Add User"

You can add more users later:
- `contact@methanemitigationpartners.com`
- `info@methanemitigationpartners.com`
- `brennan@methanemitigationpartners.com`

## Step 5: Update Privacy Policy Email

Once your email is active, update the privacy page:

Edit `/Users/jefflevine/MMP/privacy.html`:
```html
Change: privacy@methanemitigationpartners.com
To: contact@methanemitigationpartners.com (or whatever you created)
```

## Step 6: Set Up Email Client

### Option A: Gmail Web (Recommended)
- Go to https://gmail.com
- Sign in with: `jeff@methanemitigationpartners.com`
- Use the password you created

### Option B: Apple Mail
1. Open Mail app
2. Mail → Add Account → Google
3. Enter: `jeff@methanemitigationpartners.com`
4. Sign in with Google

### Option C: Outlook
1. File → Add Account
2. Enter: `jeff@methanemitigationpartners.com`
3. Follow prompts

## Step 7: Test Email

1. Send a test email to yourself: `jeff@methanemitigationpartners.com`
2. Check if it arrives
3. Reply to confirm sending works

## Step 8: Add Email Aliases (Optional)

You can create aliases that forward to your main account:

In Google Admin:
1. Users → Select user → User information
2. Email aliases → Add alias
3. Add:
   - `contact@methanemitigationpartners.com`
   - `info@methanemitigationpartners.com`
   - `privacy@methanemitigationpartners.com`
   - `support@methanemitigationpartners.com`

All emails to these addresses will go to your main inbox.

## Verification Checklist

- [ ] Google Workspace account created
- [ ] Domain verified with TXT record
- [ ] MX records added to GoDaddy (all 5)
- [ ] Waited 30 minutes for DNS propagation
- [ ] Primary email account created
- [ ] Test email sent and received
- [ ] Email client configured (Gmail/Mail/Outlook)
- [ ] Privacy policy email updated
- [ ] Aliases added (optional)

## Troubleshooting

**Email not arriving after 30 minutes?**
1. Check MX records in GoDaddy are correct
2. Use Google's MX record checker: https://toolbox.googleapps.com/apps/checkmx/
3. Check DNS propagation: https://www.whatsmydns.net/

**Can't verify domain?**
1. Make sure TXT record is added to GoDaddy
2. Wait 15 minutes and try again
3. Check the TXT record value matches exactly what Google provided

**Wrong MX records?**
1. Delete ALL existing MX records first
2. Add only the 5 Google MX records
3. Make sure Priority values are correct (1, 5, 5, 10, 10)

## Cost

- **Business Starter**: $6/user/month
- **Business Standard**: $12/user/month
- **Business Plus**: $18/user/month

You can start with 1 user ($6/month) and add more later as needed.

## Additional Features

Google Workspace includes:
- Gmail (custom domain email)
- Google Drive (30GB+ per user)
- Google Calendar (team calendars)
- Google Meet (video calls)
- Google Docs, Sheets, Slides
- Shared team drives
- Admin controls

All integrated with your custom domain.

## Next Steps After Email Works

1. Update website contact forms (if any) to send to your new email
2. Add email signature with MMP branding
3. Set up email forwarding rules if needed
4. Configure spam filters
5. Add mobile email access (iPhone/Android)

Your professional email setup will be complete!
