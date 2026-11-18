# ripplesystems.io

The Ripple Systems website, first revision (2026-11-18). Plain HTML and CSS, no
build step: any static host serves it as it is.

| Path | Page |
|---|---|
| `/` | Home: hero, homeowner/dealer band, how it works, dealer specs, features, panel and app showcase, dealer promo, contact |
| `/support/` | Support (the App Store's Support URL) |
| `/privacy/` | Privacy Policy (the App Store's Privacy Policy URL) |

Layout follows tidedrycleanerstx.com (hero, two-up action band, three icon
steps, pale stats band, dark tile grid, promo card, contact band); colours are
Ripple's (`styles.css`, `:root`). The panel images are crops of the dealer
flyer; the phone screenshots come from the app's demo mode.

## Preview

```sh
cd RippleWebsite && python3 -m http.server 8765
```

then open http://localhost:8765. Links are root-relative (`/assets/…`), so
opening `index.html` straight from Finder shows the page without styles.

## Putting it live (GitHub Pages, free)

1. Make a GitHub repo (for example `ripplesystems.io`), push this folder to it.
2. Repo → Settings → Pages → deploy from the `main` branch, root folder. The
   `CNAME` file already names `ripplesystems.io`.
3. At the domain's DNS host, add for the bare domain four `A` records:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`,
   and a `CNAME` for `www` pointing to `<github-user>.github.io`.
   Leave the existing `mqtt` and `push` records alone: the spas and the app
   use them.
4. Back in Settings → Pages, tick **Enforce HTTPS** once the certificate is
   issued (usually within an hour).

## To update

- Privacy or support text: edit `privacy/index.html` or `support/index.html`,
  and keep the app's `PrivacyInfo.xcprivacy` and the App Store Connect privacy
  answers in step with the policy.
- When the app is live, replace "coming soon" in the announcement bar and the
  homeowner column with the App Store link.
