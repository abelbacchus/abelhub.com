# abelhub.com

The site, as static files for GitHub Pages. No build step: what is here is what is served.

```
index.html              home
about.html              the studio
contact.html            support, pointing at the service desk
apps/multazam.html      Multazam's product page
legal/                  Multazam's privacy policy and support page
assets/                 simulator captures, replaceable
tokens.css base.css     design tokens and base rules (Hallmark, theme Studio)
site.css                the page styles; the Hallmark stamp is its first line
```

## Publishing

Settings → Pages → Deploy from a branch → `main` / root. `CNAME` already names the
domain; `.nojekyll` stops Jekyll touching the files.

DNS, in Route 53, replacing the WordPress A record:

| Type | Name | Value |
| --- | --- | --- |
| A | abelhub.com | 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 |
| CNAME | www | `<user>.github.io` |

Then tick **Enforce HTTPS** once the certificate is issued.

## Replacing a picture

Every screenshot is a plain file in `assets/`, captured from the simulator with a 9:41
status bar (`xcrun simctl status_bar <udid> override --time 9:41 ...`). Replace a file
and the page picks it up; keep the width and height attributes in step.
