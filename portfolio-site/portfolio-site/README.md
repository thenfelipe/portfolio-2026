# Felipe Valenzuela — Portfolio site

Plain static HTML/CSS site. No build step, no dependencies. Every page works by just opening the `.html` file, or by hosting the folder as-is.

## Structure

```
index.html          Homepage (hero + preview of both work sections)
work.html            Full case list (all 7 cases)
brand-pr.html        Brand, PR & storytelling section landing page
about.html           Full bio + experience timeline
work/*.html          One page per case study
assets/css/style.css Shared stylesheet
assets/img/          Photos, posters, campaign visuals
assets/video/        Short video clips used in case studies
```

## Privacy

This site is configured to opt out of search engine indexing:

- `robots.txt` at the root tells well behaved crawlers (Google, Bing) not to index anything
- Every page also has `<meta name="robots" content="noindex, nofollow">` in its `<head>`, which is the directive search engines actually respect most reliably

**Important limits to understand:**

- This makes the site *unlisted*, not *private*. Anyone who has the exact URL can still open it, that's what makes it shareable with recruiters.
- Because the GitHub repository backing this site is public (required for GitHub Pages on the free plan), the raw files are also technically fetchable directly from GitHub itself (for example via `raw.githubusercontent.com`) by anyone who finds the repository, independent of the noindex tags. The noindex tags stop search engines from surfacing the *site*, but the repo itself is still a public GitHub repo.
- If you ever want the underlying files to be genuinely private (not just unlisted), that requires either a paid GitHub plan (Pro/Team, for Pages from a private repo) or a different host with real access control, like Cloudflare Pages behind Cloudflare Access.

## Before publishing, replace the placeholders

- **LinkedIn link** — every page has a "LinkedIn" button pointing to `#`. Search and replace `href="#" target="_blank" rel="noopener">LinkedIn` with your real profile URL.
- **CV / Resume link** — same placeholder pattern, either link to a hosted PDF or remove the button.

There's no email or phone number on the site by design, the link itself is meant to be shared privately once you're already in touch with someone, not discovered cold.

## How to publish it for free

### Option A — Netlify (easiest, no account needed to start)

1. Go to **app.netlify.com/drop**
2. Drag the whole `site` folder (the one containing `index.html`) onto the page
3. Netlify gives you a live URL immediately (something like `random-name-123.netlify.app`)
4. Optional: create a free account to keep the site permanently and rename the subdomain, or connect a custom domain

### Option B — GitHub Pages (best if you also want version control)

1. Create a new repository on GitHub, e.g. `felipe-portfolio`
2. Upload the contents of the `site` folder to the repository root (not inside a subfolder)
3. Go to the repo's **Settings → Pages**
4. Under "Build and deployment", set **Source: Deploy from a branch**, branch **main**, folder **/(root)**
5. Save. Your site will be live in a minute or two at `https://yourusername.github.io/felipe-portfolio/`
6. Optional: add a custom domain under the same Pages settings

### Option C — Vercel

1. Go to **vercel.com**, sign up free, click **Add New → Project**
2. Choose "Deploy without Git" / drag and drop the `site` folder
3. Live URL in seconds, custom domains supported free

All three are genuinely free for a static site like this one, with no traffic limits that would realistically affect a portfolio.

## A note on file size

The `assets/video` folder currently holds three short clips (under 2MB each) so the whole site stays fast to load and safely under GitHub's per-file upload limit. If you want to add more of the original video footage from the deck, keep individual files under roughly 20–30MB so pages still load quickly, and avoid anything over 100MB (GitHub will reject the push).
