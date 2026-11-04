# Azmy Ehab — Official Portfolio

**Official website:** <https://azmyehab.cc/>  
**GitHub profile:** <https://github.com/AZMYEHAB21>  
**Target repository:** <https://github.com/AZMYEHAB21/Azmy-Ehab-Portfolio>

A bilingual (English / Arabic) personal portfolio for **Azmy Ehab (عزمي إيهاب)**. The site keeps its original visual identity, projects, certificates and learning content. It is a static GitHub Pages project: no build system, framework, backend, secrets or package installation is required.

## Features

- Responsive layout for mobile, tablet and desktop.
- English / Arabic content with LTR / RTL direction switching.
- Dark / light themes, with language and theme preferences saved in the browser when storage is available.
- Original portfolio sections: About, Skills, Projects, Certificates, Education, Learning Journey and Contact.
- Four existing project cards and five certificate records, with original PDFs retained in the repository.
- Local Bootstrap 5.3.3 assets; custom JavaScript enhancements are in `js/main.js`.
- Reduced-motion support, keyboard-accessible controls, scroll reveals, an interactive hero cube and an optional canvas effect.
- SEO metadata, Open Graph and Twitter cards, Person + WebSite JSON-LD, `robots.txt`, `sitemap.xml` and the GitHub Pages `CNAME` file.

## Featured projects

The four existing project cards and their destinations remain part of the portfolio:

| Project | Repository | Existing live URL |
|---|---|---|
| DIVA-STOR | [GitHub](https://github.com/AZMYEHAB21/DIVA-STOR) | [Open site](https://azmyehab21.github.io/DIVA-STOR/) |
| Social-media | [GitHub](https://github.com/AZMYEHAB21/Social-media) | [Open site](https://azmyehab21.github.io/Social-media/) |
| krast-alnqwt | [GitHub](https://github.com/AZMYEHAB21/krast-alnqwt) | [Open site](https://azmyehab21.github.io/krast-alnqwt/) |
| Athar (repository name `-`) | [GitHub](https://github.com/AZMYEHAB21/-) | [Open site](https://azmyehab21.github.io/-/) |

The repository destinations were checked and resolve to existing GitHub repositories. Public availability of the four live Pages sites was not tested in this environment.

## Project structure

```text
.
├── index.html
├── CNAME
├── robots.txt
├── sitemap.xml
├── README.md
├── GOOGLE-SEARCH-CONSOLE-GUIDE.md
├── PROJECT-AUDIT-REPORT.md
├── apple-touch-icon.png
├── favicon.ico
├── favicon.svg
├── favicon-48x48.png
├── favicon-96x96.png
├── assets/
│   ├── certificates/       # original certificate images and PDFs
│   ├── images/             # portrait image
│   ├── projects/           # project screenshots
│   └── vendor/             # local Bootstrap CSS and JS
├── css/style.css
├── js/main.js
└── docs/screenshots/       # portfolio screenshots used in documentation
```

## Run locally

The project has no build step. From this directory, run:

```bash
python -m http.server 8000
```

Then open <http://localhost:8000/>. Opening `index.html` directly may also work, but a local HTTP server is recommended because it behaves more like GitHub Pages.

## Deploy to the target GitHub repository

Target repository: <https://github.com/AZMYEHAB21/Azmy-Ehab-Portfolio>

1. Create the repository under the `AZMYEHAB21` account if it does not already exist. The repository should be public for GitHub Pages on GitHub Free.
2. Upload the **contents** of this project folder to the repository root. Do not upload the enclosing `Portfolio1-main` folder; `index.html`, `CNAME`, `robots.txt` and `sitemap.xml` must be at the repository root.
3. Commit the files to the `main` branch.
4. Open **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**, select `main`, select `/(root)`, then save.
6. Under **Custom domain**, enter exactly `azmyehab.cc` and save. Keep the root-level `CNAME` file containing exactly `azmyehab.cc`.
7. After DNS has propagated and GitHub has issued the TLS certificate, enable **Enforce HTTPS** in the same Pages settings area.

The repository's default `github.io` address is only the hosting endpoint. The official public/canonical website remains **https://azmyehab.cc/**. The HTML canonical, Open Graph URL, JSON-LD URLs, `robots.txt` sitemap declaration and `sitemap.xml` all use the official domain.

## DNS records for GitHub Pages

Configure these records with the DNS provider that manages `azmyehab.cc`:

| Type | Host / Name | Value |
|---|---|---|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `AZMYEHAB21.github.io` |

Do not create a CNAME at the apex (`@`) alongside the A records. Remove conflicting parking/forwarding records for the same host. Do not point `www` to the repository path; it must point directly to `AZMYEHAB21.github.io`. When both apex and `www` records are configured and the apex domain is selected in Pages, GitHub Pages can redirect the `www` variant to the apex domain.

Before changing DNS, compare the zone with the records currently in use so you do not accidentally remove unrelated mail or verification records. GitHub recommends verifying ownership of a custom domain in GitHub account settings before attaching it to a repository. DNS updates can take time to propagate, and HTTPS may not become available immediately.

Official references:

- [GitHub Pages: managing a custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
- [GitHub Pages: securing your site with HTTPS](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)

## Technical SEO notes

- Primary URL and canonical: `https://azmyehab.cc/`.
- There is one indexable HTML page, so the sitemap intentionally contains only the homepage. The certificate PDFs and image assets are supporting files, not separate HTML pages to list in the sitemap.
- `robots.txt` allows normal crawling and points to the sitemap.
- No Search Console verification token has been fabricated or inserted. Google supplies a unique DNS TXT value after you add the Domain property.
- No `noindex` directive is present.
- The old Social-media site remains listed as a separate project/page, not as the official portfolio URL.

For the DNS verification, sitemap submission, URL Inspection and indexing workflow, follow [GOOGLE-SEARCH-CONSOLE-GUIDE.md](GOOGLE-SEARCH-CONSOLE-GUIDE.md).

## Content integrity

The original portfolio sections, certificate images, certificate PDFs, project screenshots and project destinations are retained. Project repository links point to existing repositories under `AZMYEHAB21`. No certificate verification links, awards, testimonials, statistics or other achievements have been invented. Where an official certificate verification URL has not been supplied, the site simply does not display a verification link.

## Browser and dependency notes

- Bootstrap is stored locally under `assets/vendor/`.
- Google Fonts are loaded from Google Fonts; system font fallbacks remain in the CSS if the external font service is unavailable.
- Current evergreen Chrome, Edge, Firefox and Safari are the intended browsers.
- The site is static and does not require Node.js, npm, a database, API keys or a server-side runtime.

## نبذة بالعربية

هذا هو الموقع الشخصي الرسمي لعزمي إيهاب على الدومين `https://azmyehab.cc/`. المشروع ثابت ويعمل على GitHub Pages دون إطار عمل أو خطوة Build. يحتفظ بالأقسام والمشروعات والشهادات الأصلية، ويدعم العربية والإنجليزية واتجاهي RTL/LTR والوضعين الداكن والفاتح. تم ضبط canonical وملفات `robots.txt` و`sitemap.xml` وبيانات Schema.org على الدومين الرسمي فقط.

للنشر: ارفع محتويات هذا المجلد مباشرة إلى جذر مستودع `AZMYEHAB21/Azmy-Ehab-Portfolio`، ثم اختر `main / (root)` في إعدادات GitHub Pages، واضبط Custom domain على `azmyehab.cc`. بعد ذلك اتبع [دليل Google Search Console](GOOGLE-SEARCH-CONSOLE-GUIDE.md).
