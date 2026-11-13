# Stream-Flaflix OAuth pages

Public homepage and privacy policy for the Google OAuth consent screen.

**Do not use a plain `github.io` address as the Google authorized domain.** Google treats
`github.io` as a public suffix and rejects it with `Domain not found`. Use a custom domain you
own, for example `legal.flaflix.top`, and verify the top private domain (`flaflix.top`) in Google
Search Console.

## Publish the Pages site

1. Create a public GitHub repository, for example `stream-flaflix-legal`.
2. Push the four files in this folder (`index.html`, `privacy.html`, `style.css`, `.nojekyll`) to
   the `main` branch root.
3. In the repository, open **Settings → Pages**.
4. Set **Source** to **Deploy from a branch**, branch **main**, folder **/(root)**, then **Save**.
5. Under **Custom domain**, enter `legal.flaflix.top` (or another subdomain you prefer) and save.
6. At your DNS provider, add a `CNAME` record for `legal` pointing to `<github-username>.github.io`.
   Set it to **DNS only** if the provider is Cloudflare, then enable **Enforce HTTPS** in GitHub
   Pages once the certificate is ready.

## Google Auth Platform

In **Google Auth Platform → Branding**:

- Application home page: `https://legal.flaflix.top/`
- Application privacy policy: `https://legal.flaflix.top/privacy.html`
- Authorized domain: `flaflix.top` (add this first and verify it in Search Console)
- App name: `Stream-Flaflix`

Save Branding, return to **Audience**, and click **Publish app**. If the button stays disabled,
confirm both URLs return 200 and the domain is verified by the same Google account that owns the
Cloud project.

Publishing changes newly issued tokens only. Reconnect Google Drive once afterward to replace the
Testing-mode token with a production token.
