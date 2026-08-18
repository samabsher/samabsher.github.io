# Publishing checklist

## 1. Push to GitHub (once)

1. Create an empty repository on github.com (e.g. `samabsher.com`), no README.
2. Then:

```
cd D:\repos\samabsher.com
git remote add origin https://github.com/<USERNAME>/samabsher.com.git
git push -u origin master
```

Git Credential Manager will pop up a browser window to sign in the first time.

## 2. Turn on GitHub Pages

On github.com: repository → Settings → Pages → "Deploy from a branch" →
branch `master`, folder `/docs` → Save. The site appears at
`https://<USERNAME>.github.io/samabsher.com/` within a minute or two.

## 3. Custom domain (samabsher.com)

1. Buy the domain at a registrar (Porkbun, Cloudflare, Namecheap — ~$10/yr).
2. In the registrar's DNS settings add:
   - Four `A` records for `@` (apex): `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`
   - One `CNAME` record: `www` → `<USERNAME>.github.io`
3. On github.com: Settings → Pages → Custom domain → `samabsher.com` → Save,
   and tick "Enforce HTTPS" once the certificate is issued (can take an hour).
4. Locally, create a file named `CNAME` (no extension) in the project root
   containing exactly `samabsher.com`, and add this line under `project:` in
   `_quarto.yml` so it is copied into `docs/` on every render:

```yaml
project:
  type: website
  output-dir: docs
  resources:
    - CNAME
```

5. `quarto render`, commit, push.

Do NOT add the CNAME file before the domain is purchased and the DNS records
exist — it would break the github.io address in the meantime.
