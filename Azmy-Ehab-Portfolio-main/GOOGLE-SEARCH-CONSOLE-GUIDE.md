# Google Search Console setup — azmyehab.cc

This guide is for the official portfolio domain **azmyehab.cc**. Keep that domain as the primary site address. Do not submit the `github.io` repository URL as the canonical website.

## 1. Add the domain property

1. Open [Google Search Console](https://search.google.com/search-console/).
2. Sign in with the Google account that should own the website property.
3. Open the property selector and choose **Add property**.
4. Choose **Domain** (not URL prefix).
5. Enter `azmyehab.cc` without `https://`, `www`, or a trailing slash.
6. Continue. Search Console will display a DNS verification record for your domain.

A Domain property covers the root domain and its subdomains/protocol variants. Domain properties are verified through DNS ownership.

## 2. Verify ownership with DNS TXT

1. In the Search Console verification dialog, copy the complete TXT value Google generated. It usually begins with `google-site-verification=`; the suffix is unique to your property and Google account.
2. Sign in to the DNS provider that manages `azmyehab.cc`.
3. Open DNS management / Zone Editor and add a **TXT** record.
4. For the host/name field, use `@` or leave it blank according to the DNS provider's interface. For the value/content field, paste the exact string copied from Search Console.
5. Keep the existing GitHub Pages A records and `www` CNAME record. Add the TXT record alongside them; do not replace the website records.
6. Save the record. Return to Search Console and click **Verify**.
7. If Google cannot see it yet, confirm the host and value are exact and try again after DNS has propagated. Keep the TXT record in place after verification.

**Important:** Do not copy a sample verification token from a tutorial or invent one. Use only the exact token generated inside your own Search Console property.

## 3. Submit the sitemap

After the domain property is verified and the site has been deployed:

1. Open the `azmyehab.cc` property in Search Console.
2. In the left menu, open **Indexing → Sitemaps**.
3. In **Add a new sitemap**, enter `sitemap.xml`.
4. Submit it. The resulting URL should be `https://azmyehab.cc/sitemap.xml`.
5. Check the submission status and discovered URL count. This portfolio is currently a one-page site, so the sitemap contains only `https://azmyehab.cc/`.

The same sitemap URL is also declared in `robots.txt` at `https://azmyehab.cc/robots.txt`.

## 4. Inspect the homepage

1. In the Search Console URL Inspection bar, enter exactly `https://azmyehab.cc/`.
2. Review the current Google Index information if available.
3. Confirm that the user-declared canonical is `https://azmyehab.cc/`.
4. If Google reports a different Google-selected canonical, open the details and investigate the alternate URL, redirect or duplicate signals before requesting indexing.

## 5. Run Test Live URL

1. From the URL Inspection result, select **Test Live URL**.
2. Wait for the live test to complete.
3. Review page availability, crawl permission, indexing permission and the rendered page.
4. Check the fetched HTML for the canonical URL and confirm that Google can retrieve page resources such as CSS, JavaScript and images.
5. A successful live test means Google can fetch and parse the URL under the test conditions; it is not a guarantee that Google will index it.

## 6. Request indexing

When the live test shows that the homepage is available to Google:

1. Return to the URL Inspection result for `https://azmyehab.cc/`.
2. Select **Request Indexing**.
3. Wait for Search Console to accept the request. Repeated requests are not necessary.

Submitting a request does not guarantee inclusion in Google Search. Google decides when and whether to index a page based on its systems and policies.

## 7. Monitor results and fix issues

Check these areas periodically:

- **Indexing → Pages:** review indexed, not-indexed and excluded URL groups. Open each reason and inspect affected URLs.
- **Sitemaps:** confirm that `sitemap.xml` was fetched and parsed successfully.
- **URL Inspection:** recheck the homepage after major edits and confirm the declared and selected canonical URLs.
- **Experience / Core Web Vitals:** review field data when enough real-user data becomes available.
- **Security & Manual Actions:** check for security problems or manual actions.

For this one-page portfolio, investigate unexpected URLs, `github.io` variants, old portfolio URLs or HTTP/`www` variants showing as separate indexable pages. Keep the apex URL `https://azmyehab.cc/` as the intended canonical.

## Official Google help pages

- [Add a property to Search Console](https://support.google.com/webmasters/answer/34592)
- [Verify site ownership with a DNS record](https://support.google.com/webmasters/answer/9008080)
- [Sitemaps report](https://support.google.com/webmasters/answer/7451001)
- [URL Inspection tool](https://support.google.com/webmasters/answer/9012289)
