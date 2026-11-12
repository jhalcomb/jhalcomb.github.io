# jHal Labs website

A polished, lightweight website for **jHal Labs**, ready for **GitHub Pages**. The site uses plain HTML/CSS and a tiny JavaScript file. No Node/npm, build system, external fonts, cookies, or website analytics are required.

## What you get

- **Home page:** jHal Labs branding, games, studio information, responsive mobile navigation.
- **Games:** NineRally Sudoku, WordSearch Rally, Word Scramble Rally.
- **Game-specific privacy policy URLs** for Apple's App Store Connect.
- **Support page** with contact and a few FAQs.
- Custom SVG favicon and graceful 404 page.

## IMPORTANT — do these steps before publishing or submitting an app

### 1. Add your support email

Once you create your new jHal Labs email address, search for this exact text in the downloaded files and replace it with the real address:

`REPLACE_WITH_YOUR_SUPPORT_EMAIL`

You will find it on the Support page and the three individual privacy pages. You can open each HTML file in a text editor (VS Code, for example) and use Find/Replace across files.

**Do not submit the pages to Apple with the placeholder left in place.**

### 2. Review the privacy policies against the actual release builds

The policies are **drafts based on the intended local-multiplayer setup**, not audited statements. I did not inspect the final app binaries or all dependencies while preparing this website. Before publishing, confirm all claims, particularly:

- Whether display names, local network info, gameplay states, or device identifiers are shared.
- Whether there are ads, analytics, crash reporting SDKs, Game Center, iCloud, or other third-party services.
- Whether any gameplay or user data is transmitted to a server.
- Whether local data persists after uninstall or through cloud backup.
- Whether the game is targeted at children or has any special data practices.
- Whether the supported device labels (iPhone/iPad) are current.

Update the policies and **App Store Connect App Privacy questionnaire** so they agree with your final app behavior. If you add SDKs or online features, revise the text before publishing. Check Apple's current guidelines before submission.

### 3. Update the game release status

The homepage says the three games are **coming soon** and does **not** link to App Store listings. Once a game is live, edit `index.html` to replace its `App Store release coming soon` label with an actual App Store link. Never guess an App Store listing URL before it exists.

## Publish to GitHub Pages — easiest option

If your new GitHub username is `jhallabs`, use the repository name **`jhallabs.github.io`**. If your actual username is different, substitute **`YOUR-USERNAME.github.io`** in the steps below. The username is not the app name; GitHub uses it to determine the personal Pages URL.

1. Sign in to your new GitHub account and create a **public** repository named `YOUR-USERNAME.github.io`.
2. Upload the **contents** of this website folder to the repository root, so `index.html`, `privacy/`, `support/` and `assets/` are at the top level (not inside another folder).
3. Open the repository's **Settings → Pages**.
4. In **Build and deployment**, choose **Deploy from a branch**, branch **main**, folder **/(root)**. Click **Save**.
5. After GitHub publishes, your site is available at `https://YOUR-USERNAME.github.io/` (assuming this is a user Pages repository). Site deployment can take several minutes.

Official GitHub documentation: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

### Optional: your own domain

If you later register `jhallabs.com` or another domain, you can configure a **custom domain** in GitHub Pages and point DNS at GitHub. You **do not** need a paid domain to use these privacy policy links.

## Enter these links in App Store Connect

Substitute `YOUR-USERNAME` with the actual GitHub username. You must publish the site before the links will work.

| App | Privacy Policy URL |
| --- | --- |
| NineRally Sudoku | `https://YOUR-USERNAME.github.io/privacy/ninerally-sudoku.html` |
| WordSearch Rally | `https://YOUR-USERNAME.github.io/privacy/wordsearch-rally.html` |
| Word Scramble Rally | `https://YOUR-USERNAME.github.io/privacy/word-scramble-rally.html` |

In **App Store Connect → [app] → App Privacy → Edit (Privacy Policy)**, enter that game's URL. Apple also expects a privacy policy link **inside the app**, so add a small link in each game's Settings, About, or Help screen pointing to the same public URL. Verify your policies are accurate before entering the URLs.

Official Apple documentation: https://developer.apple.com/help/app-store-connect/manage-app-information/manage-app-privacy/

## Test the site locally

Simplest: double-click `index.html` to open in a browser. For more predictable links, run a local HTTP server **from this folder**:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000/ and check the mobile layout (in your browser's device toolbar).

## Website files

```text
index.html
404.html
.nojekyll
assets/
  styles.css
  app.js
  favicon.svg
privacy/
  index.html
  ninerally-sudoku.html
  wordsearch-rally.html
  word-scramble-rally.html
support/
  index.html
README.md
```

## Editing and maintenance

- Colors, spacing, fonts, and layouts: `assets/styles.css`.
- Navigation, home page descriptions, and game cards: `index.html`.
- Support contact and FAQs: `support/index.html`.
- Policy text/dates: `privacy/*.html`.
- Brand: `<jHal /> Labs` rendered with CSS/HTML (no proprietary fonts).
- Adding a new game: add a card on the home page and a new app-specific policy page. Add the policy to the privacy index and footer/sidebar links if relevant.
- When you edit your site, commit/push the changes to GitHub and Pages republishes automatically.
