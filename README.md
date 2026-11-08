# Prabhakar: Personal Portfolio

A seven-page personal portfolio built with plain HTML, CSS and vanilla JavaScript. No build tools, no frameworks, no paid services. Light theme by default, with a dark theme. Laptop-first and responsive down to 320px wide.

Status: Stage 7 (final quality assurance) complete. See `project-notes/QA-REPORT-STAGE7.md`.

## Files

```
index.html  about.html  projects.html  skills.html
experience.html  achievements.html  contact.html
css/styles.css          Design tokens, light and dark themes, all page styles
js/main.js              Shared header and footer, theme switch, mobile menu
js/contact.js           Contact form validation (contact page only)
js/certificates.js      Certificate list (achievements page only)
assets/documents/       Prabhakar-Kumar-CV.pdf (the Download CV file, no phone number)
assets/images/          favicon.svg
sitemap.xml  robots.txt  .nojekyll
project-notes/          Deployment guide, QA report and earlier stage reports (not needed online)
```

The header and footer are not in the HTML files. `js/main.js` builds them on every page.

## Editing

- Name, email, LinkedIn, GitHub, menu: the `SITE` and `NAV` blocks at the top of `js/main.js`.
- Certificates: the `CERTIFICATES` list in `js/certificates.js` (title, optional issuer, date, description, real link). Add only what you can verify.
- CV: replace `assets/documents/Prabhakar-Kumar-CV.pdf`, keeping the same name.
- Colours and fonts: the `:root` variables at the top of `css/styles.css`.
- Web address: pages use `https://prabhakar70.github.io/` in `canonical` and `og:url`, in `sitemap.xml` and in `robots.txt`. Change all three if the site lives at a different address.

## Content rules

Only verified information is used. Sales Prediction R² and RMSE values stay off the site, Matplotlib is not tied to a project, and Joblib appears only in the general Tools lists. The contact form validates in the browser only and sends nothing; it says so on the page.

## Testing locally

Open a terminal in this folder and run `python3 -m http.server 8000`, then visit http://localhost:8000. Opening the files by double-click also works for most pages.

## Deploying (free)

Follow `project-notes/DEPLOYMENT-GUIDE.md` (GitHub Pages, step by step).

## Known limits

- Fonts come from Google Fonts. If blocked, the site falls back to system fonts.
- No `og:image` (no verified image exists). Link previews show text only.
- The contact form is not connected to any service.
- The AWS SBG badge image is loaded from Credly (images.credly.com) because it could not be downloaded here. If it cannot load, the card shows text only. To host it yourself, save the badge image from your Credly page as `assets/images/aws-sbg-badge.png` and change the `src` of the `.badge-card img` on `index.html` and `experience.html`.
