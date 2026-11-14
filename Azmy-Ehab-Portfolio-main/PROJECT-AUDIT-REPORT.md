# Project audit and QA report

**Audit date:** 4 November 2026  
**Source archive:** `Portfolio1-main.zip`  
**Official domain configured in the project:** `https://azmyehab.cc/`

## Delivered changes

- Updated the document title and search description, and added complete Open Graph and Twitter Card metadata.
- Set the canonical URL, Open Graph URL, Person URL, WebSite URL, structured-data image and sitemap to the official apex domain `https://azmyehab.cc/`.
- Replaced the single Person JSON-LD block with a valid JSON-LD graph containing `Person` and `WebSite`, using only profile and skill details already present in the portfolio.
- Kept `CNAME` at the repository root with the exact value `azmyehab.cc`.
- Kept `robots.txt` crawlable and pointed it to the root sitemap. The sitemap contains only the homepage because the portfolio has one indexable HTML document.
- Changed favicon and touch-icon paths to relative references so they work both at the custom-domain root and beneath the repository path on the default GitHub Pages host.
- Kept the existing About, Skills, Projects, Certificates, Education, Learning Journey and Contact content, as well as all four project cards, five original certificate PDFs, certificate previews, screenshots and portrait assets.
- Removed inactive placeholder verification-link comments rather than inventing verification URLs. No certificate card lost its original view/open actions.
- Clarified that the old Social-media URL is a separate project/page, not the official portfolio homepage.
- Fixed the mobile navigation close handler, made the interactive SQL console title keyboard-operable, added an automatic copyright year and reduced unnecessary canvas/pointer animation work.
- Updated this README with current publishing and DNS instructions, and added the dedicated Google Search Console guide.

## Local and static test results

| Test | Result |
|---|---:|
| HTML documents parsed | 1 |
| HTML parser errors | 0 |
| Main page sections | 9 |
| H1 elements | 1 |
| IDs checked / duplicates | 33 / 0 |
| Images in HTML / missing `alt` | 16 / 0 |
| HTML anchors checked | 29 |
| Unique local resource paths / missing files | 23 / 0 |
| Broken in-page anchor targets | 0 |
| Local HTTP requests / non-200 responses | 27 / 0 |
| Repository-subpath relative references / non-200 responses | 18 / 0 |
| JavaScript syntax checks passed | 2 of 2 |
| CSS files parsed / parse errors | 2 / 0 |
| Raster image files verified | 20 |
| PDF file signatures checked / invalid signatures | 5 / 0 |

Additional SEO assertions passed locally:

- Exactly one canonical link points to `https://azmyehab.cc/`.
- `robots` is `index, follow, max-image-preview:large`; no `noindex` directive was found.
- The JSON-LD parses as JSON and declares `Person` and `WebSite`.
- Nine Open Graph tags and five Twitter tags are present.
- `sitemap.xml` parses as XML and contains only `https://azmyehab.cc/`.
- `robots.txt` allows crawling and declares `https://azmyehab.cc/sitemap.xml`.
- The root `CNAME` contains only `azmyehab.cc`.
- All 27 local HTTP checks returned HTTP 200, including the HTML page, SEO files, scripts, styles and referenced assets.
- A local simulation under `/Azmy-Ehab-Portfolio/` confirmed that the 18 relative `src` and `link` resources resolve beneath a project subpath.
- GitHub repository metadata lookups confirmed that all four referenced project repositories exist: `DIVA-STOR`, `Social-media`, `krast-alnqwt` and `-`.

## Checks that could not be completed here

These are intentionally **not** marked as passed:

1. **Public-domain HTTPS, DNS and redirects:** outbound DNS resolution failed in the execution environment. I could not fetch `azmyehab.cc`, `www.azmyehab.cc`, or the target `github.io` URL from this environment. The current live HTTPS certificate, apex DNS records and `www` redirect therefore remain unverified.
2. **Browser-rendered mobile/desktop interaction:** browser navigation through the available Chromium/Playwright environment was blocked by the environment. The source CSS and relative paths were checked, but I cannot claim a real visual viewport test or live interaction test across phone/tablet/desktop widths.
3. **Googlebot and Search Console:** no Googlebot live fetch, URL Inspection test, ownership verification or sitemap submission was performed. These require the deployed public URL and the owner's Search Console / DNS-provider access.
4. **Target repository access:** the GitHub connector returned 404 for `AZMYEHAB21/Azmy-Ehab-Portfolio`, and public repository search returned no result. The repository may not yet exist or may be private/unavailable to the connected GitHub integration. No files were pushed and no repository settings were changed.
5. **External live project URLs:** the four GitHub repositories were confirmed, but their linked GitHub Pages deployments were not live-tested from this environment.

## Final status

The ZIP is prepared as a static GitHub Pages source package, with the custom-domain and SEO files in place. The source-level checks above passed. Before treating the live website as fully verified, upload it to the target repository, configure Pages and DNS, enable HTTPS after GitHub makes it available, then complete the live checks listed in `GOOGLE-SEARCH-CONSOLE-GUIDE.md`.
