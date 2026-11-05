# Launch checklist

Code and content are moved separately:

- **Child theme** (this repo): deploy only `themes/The-Matting-Company/`. Do not deploy `docs/` or the project files to the web root.
- **Everything else** (database + uploads): move it once, at launch, with a migration tool, and replace `http://matting-company-revamp.local` with `https://themattingcompany.ie`. This includes the custom code, which is stored in the WPCode plugin. After launch, never overwrite the production database.

## Before

- [ ] Take a full backup of the current live site.
- [ ] Export the Redirection rules (JSON) from live, if it has any.
- [ ] Check the live site's Code Snippets plugin and either port or drop each snippet.
- [ ] Check the live site's Complianz settings and GTM / analytics IDs.
- [ ] Get sign-off on the open content items: About Us copy, the Solutions page (supplier and price are public), and the Clayton Cork and The Masonry pages (both show Center Parcs content on live).

## Go live

- [ ] Migrate the database and uploads, and deploy the child theme.
- [ ] Check that WPCode is active and all the "TMC: …" snippets are active under Code Snippets.
- [ ] In `wp-config.php`, set `WP_ENVIRONMENT_TYPE` to `production` and `WP_DEBUG` to `false`.
- [ ] Set up SMTP so the forms send real email.
- [ ] Run the Complianz wizard: cookie banner, Consent Mode, and GTM if used.
- [ ] Check that Settings → Reading → "Discourage search engines" is off.
- [ ] Remove WordPress Importer, Child Theme Wizard, Astra/JetEngine/CPT UI leftovers if migrated, and any unused themes.
- [ ] Revoke the application passwords created during development (Users → Profile).

## After

- [ ] Run Elementor → Tools → Clear Files & Data, and purge the host cache.
- [ ] Check that the Site Guide shows all green.
- [ ] Submit each of the 6 forms and confirm the emails arrive at office@themattingcompany.ie.
- [ ] Test some old URLs, including `/contact-us/`, `/homepage/` and a category such as `/blog-post/`.
- [ ] Confirm tags fire only after the cookie banner is accepted (use Tag Assistant).
- [ ] Submit the sitemap in Google Search Console.
