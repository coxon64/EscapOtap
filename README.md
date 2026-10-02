# EscapOtap website

A static site for GitHub Pages: the home page, user manual, support page and privacy policy that
App Store Connect links to. Plain HTML and CSS, no build step.

| Page | URL once published | Used for |
|---|---|---|
| `index.html` | https://coxon64.github.io/escapotap/ | Marketing URL |
| `support/index.html` | https://coxon64.github.io/escapotap/support/ | Support URL (required) |
| `privacy/index.html` | https://coxon64.github.io/escapotap/privacy/ | Privacy Policy URL (required) |
| `manual/index.html` | https://coxon64.github.io/escapotap/manual/ | Settings › About › User Manual in the app |
| `404.html` | any wrong address | "Page not found" |

The app links to the manual URL and quotes the privacy URL, so keep these paths as they are.

## Publish it (about 5 minutes)

1. Sign in to GitHub as **coxon64** and create a new **public** repository named exactly
   **`escapotap`** (no README, no licence; leave it empty).
2. In Terminal, from this `Website` folder:

   ```bash
   cd "<project folder>/Website"
   git init -b main
   git add .
   git commit -m "EscapOtap website"
   git remote add origin https://github.com/coxon64/escapotap.git
   git push -u origin main
   ```

   (Or drag the contents of this folder, including the hidden `.nojekyll` file, into the
   repository's **Add file › Upload files** page on github.com. In Finder, press
   ⌘⇧. to show hidden files.)
3. On github.com, open the repository › **Settings › Pages**. Under **Build and deployment**, set
   **Source** to **Deploy from a branch**, **Branch** to **main** and the folder to **/ (root)**, then **Save**.
4. Wait a minute or two, then open https://coxon64.github.io/escapotap/ and click through every
   page. Check the support and privacy links work on your iPhone too.

## After the app is approved

Replace the "Coming soon to the App Store" badge in `index.html` with Apple's official
**Download on the App Store** badge (from https://developer.apple.com/app-store/marketing/guidelines/),
linking to your App Store page (`https://apps.apple.com/app/id<your app ID>`). Commit and push.

## Updating

Edit the HTML, then `git commit -am "Update" && git push`. GitHub Pages republishes in about a
minute. If the privacy policy changes, update its effective date and the in-app text in
`Keyhole/Features/Store/PrivacyPolicyView.swift` to match.

## Contents

- `assets/style.css`: the shared look (noir and brass, like the app). Pages print cleanly, so the
  manual can be printed from a browser.
- `assets/screens/`: web-sized copies of the App Store screenshots.
- `assets/fonts/`: Cinzel (SIL Open Font License; licence text alongside).
- `.nojekyll`: tells GitHub Pages to serve the files as they are.
