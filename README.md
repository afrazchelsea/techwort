# TechWort — Vercel deployment

This package is the complete static app, including its 940 vocabulary entries and original workbook PDF. No API keys, database, package installation, or build step are needed for the app.

## Deploy using GitHub (recommended for future edits)
1. Extract this ZIP. Open the `techwort` folder.
2. Create a repository in your own GitHub account.
3. Upload the contents of `techwort` to the repository root. `vercel.json` must be at the repository root, alongside `dist/`.
4. In Vercel, choose Add New > Project and import that GitHub repository.
5. Set Framework Preset to Other. Leave Root Directory at the repository root. The included vercel.json selects `dist` as Output Directory and skips build/install steps.
6. Deploy and open the production URL Vercel gives you.
7. Test the URL in a private/incognito browser window. If visitors are asked to sign in, review your project's Settings > Deployment Protection and ensure the production site is public.
8. Future pushes to the connected production branch will deploy updates.

## Deploy directly from your computer
With Node.js/npm installed, open Terminal inside the extracted `techwort` folder:

```bash
npx vercel login
npx vercel --prod
```

Select your Vercel account/team, create a new project, and use the current directory (`./`). The included configuration provides the static deployment settings.

## Preview locally
From the `techwort` folder:

```bash
python3 -m http.server 8000 --directory dist
```

Open http://localhost:8000. Use a local web server rather than double-clicking index.html because the app fetches data.json.

## What is included
- dist/index.html — page entry point
- dist/style.css — responsive styling
- dist/app.js — lessons, XP, streaks, review, lookup, and progress backup
- dist/data.json — vocabulary, examples, and guide content
- dist/workbook.pdf — original document
- vercel.json — deployment configuration

## Progress and hosting
Progress lives in each visitor's browser localStorage; there are no shared accounts or backend. To move your progress to the new domain, export it from Progress on the current site and import it on the new site. Pronunciation uses the device's speech synthesis. Fonts load from Google Fonts with system-font fallbacks.

The existing ChatGPT Sites URL remains live. Publishing to Vercel does not automatically redirect or disable it. Updates on Vercel and ChatGPT Sites are separate.

## Credits
Original workbook: Deutsch für die Tech-Welt by Zakriya Shakeel.
Original post: https://lnkd.in/p/ehcb82Uq
Duolingo-fied by Afraz Momin: https://www.linkedin.com/in/afrazm7
This package includes attribution; it does not assign a new license to the original workbook.

## Documentation
https://vercel.com/docs/builds/configure-a-build
https://vercel.com/docs/cli/deploy
