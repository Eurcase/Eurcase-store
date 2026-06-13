# Eurcase First-Stage Deployment

## 1. GitHub Private Repository

1. Sign in to GitHub.
2. Create a new private repository, for example `eurcase-website`.
3. Upload these files:
   - `index.html`
   - `src/styles.css`
   - `_headers`
   - `robots.txt`
   - `sitemap.xml`
   - `README.md`
4. Keep the repository private.
5. Turn on two-factor authentication for the GitHub account.

## 2. Cloudflare Pages

1. Sign in to Cloudflare.
2. Open `Workers & Pages`.
3. Create a Pages project.
4. Connect the GitHub repository.
5. Use these settings:
   - Framework preset: None
   - Build command: empty
   - Build output directory: `/`
6. Deploy.
7. Test the temporary Cloudflare Pages URL.
8. Turn on two-factor authentication for the Cloudflare account.

## 3. Aliyun DNS

After Cloudflare Pages gives custom domain DNS records:

1. Sign in to Aliyun.
2. Open the DNS settings for `eurcase.com`.
3. Add the records Cloudflare Pages provides.
4. Add both root domain and `www` if possible:
   - `eurcase.com`
   - `www.eurcase.com`
5. Wait for DNS to take effect.
6. Test `https://eurcase.com` and `https://www.eurcase.com`.
7. Turn on two-factor authentication for the Aliyun account.

## 4. Security Rules

For this first stage:

- Do not add a database.
- Do not add payment.
- Do not add an admin dashboard.
- Do not collect customer data until privacy, form protection, and storage are ready.

