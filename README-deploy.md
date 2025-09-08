# Deploying the 3T Technology LLC Website

This folder contains the full static site for 3T Technology LLC.

## 1) Upload to GitHub
1. Unzip `3T_site_branded.zip`.
2. Go to GitHub → New Repository (e.g., `3t-site`).
3. Upload all files/folders from this package.
4. Commit.

## 2) Connect to Netlify
1. Go to https://app.netlify.com
2. Add new site → Import from Git → select your repo.
3. Build command: *(leave blank)*
4. Publish directory: `/`
5. Deploy.

## 3) Point Your Domain (Cloudflare)
Add these DNS records in Cloudflare (Proxy: orange for A/CNAME, grey for MX/TXT):

A @ 75.2.60.5  
A @ 99.83.190.102  
CNAME www yourproject.netlify.app

MX @ 1 ASPMX.L.GOOGLE.COM.  
MX @ 5 ALT1.ASPMX.L.GOOGLE.COM.  
MX @ 5 ALT2.ASPMX.L.GOOGLE.COM.  
MX @ 10 ALT3.ASPMX.L.GOOGLE.COM.  
MX @ 10 ALT4.ASPMX.L.GOOGLE.COM.  

TXT @ v=spf1 include:_spf.google.com ~all  
TXT @ google-site-verification=xxxxxx (from Google)  
TXT google._domainkey v=DKIM1; k=rsa; p=MIIBI... (from Google)  
TXT _dmarc v=DMARC1; p=none; rua=mailto:postmaster@3ttechnologyllc.com; fo=1

## 4) Enable HTTPS
Enable Let's Encrypt SSL in Netlify after DNS propagates.

## 5) Verify
Visit https://3ttechnologyllc.com and test email to tyler@3ttechnologyllc.com.
