# Subrahmanya Hegde: cyber security portfolio

Live site: https://subrahmanyahegdeuk-eng.github.io/MyPortfolio/

A simple, static portfolio website that shows my cyber security lab work, technical projects, skills,
experience, education and training. It is plain HTML, CSS and a little JavaScript, with no frameworks,
no build step, no database, no cookies and no tracking.

## Project structure

```
portfolio/
├── index.html                  The whole page (all the text lives here)
├── css/styles.css              Colours, fonts and layout
├── js/script.js                Mobile menu, active menu highlight, footer year
├── assets/
│   ├── favicon.svg             Browser tab icon
│   ├── og-image.png            Preview image when the link is shared (1200 x 630)
│   ├── certificates/           Certificate PDFs linked from the site
│   └── resume/                 Put a public copy of your resume here as resume.pdf
└── README.md                   This file
```

## Run it locally

Double-click `index.html` and it opens in your browser. That's it.

If you prefer a local web server (closer to how it behaves once published), open a terminal in the
`portfolio` folder and run:

```
python3 -m http.server 8000
```

Then visit http://localhost:8000.

## How to edit the site

All text is in `index.html`. Search the file for these comment labels to find each part quickly:

| Label in the code | What it controls |
| --- | --- |
| `MY NAME` / `HEADLINE` | Your name and headline at the top |
| `AT A GLANCE` | The four-box summary under the hero |
| `ABOUT ME` | The About section |
| `PROJECTS: CYBER SECURITY LAB WORK` | The lab cards |
| `PROJECTS: OTHER TECHNICAL PROJECTS` | Data and AI project cards |
| `SKILLS` | Skill groups and tags |
| `EXPERIENCE` | Job history |
| `EDUCATION` | Degrees |
| `CERTIFICATIONS AND TRAINING` | Completed and in-progress training |
| `SOCIAL LINKS` | LinkedIn, GitHub and Resume buttons |
| `CONTACT DETAILS` | The Contact section |
| `SEO` | Page title, description and link preview |

Open `index.html` in any text editor (VS Code is free and easy), change the words between the tags,
save, and refresh your browser.

### Update the About section

Find `ABOUT ME` and edit the two `<p> ... </p>` paragraphs. Keep it short: two paragraphs is plenty.

### Add another cyber security project

1. Find `PROJECTS: CYBER SECURITY LAB WORK`.
2. Copy one whole block from `<article class="card" ...>` down to its matching `</article>`.
3. Paste it just before the `</div>` that closes the card grid.
4. Change the `id` values (for example `lab-sentinel` to `lab-wireshark`) in both places in that block, so
   each card has a unique id.
5. Edit the domain, title, label, short description, tags and the "View details" story.

To add a GitHub or video button to a card, put this just before `</article>`:

```html
<div class="button-row">
  <a class="btn btn-small" href="https://github.com/your-name/your-repo" target="_blank" rel="noopener noreferrer">View GitHub</a>
  <a class="btn btn-small" href="https://youtube.com/your-video" target="_blank" rel="noopener noreferrer">Watch demo</a>
</div>
```

### Replace "Details to add" placeholders

Lab cards contain lines like `<span class="todo">Details to add: ...</span>`. These show in amber on the
site so you can see what is still missing. Replace the whole `<span ...>...</span>` with your own text,
or delete the line.

Before you share the site publicly, make sure no amber "Details to add" text is left, or that you are
happy for visitors to see it.

### Update skills

Find `SKILLS`. Each group looks like this:

```html
<div class="skill-group">
  <h3>Security operations</h3>
  <ul class="tags">
    <li>SOC alert triage</li><li>Microsoft Sentinel</li>
  </ul>
</div>
```

Add a skill with another `<li>Skill name</li>`. Only add tools you have actually used.

### Add certifications

Find `CERTIFICATIONS AND TRAINING`. Copy an `<li> ... </li>` item into the **Completed** list once you
have earned something, or into **In progress** while you are studying for it. Never list an in-progress
item as completed. To add a certificate link, put
`<a href="YOUR-LINK" target="_blank" rel="noopener noreferrer">View certificate</a>` inside the item.

### Replace images

- **Favicon:** replace `assets/favicon.svg` with your own icon (keep the same file name).
- **Link preview image:** replace `assets/og-image.png` with your own 1200 x 630 pixel image.
- **Adding a screenshot to a project:** save it in `assets/` (for example `assets/sentinel-rule.png`)
  and add `<img src="assets/sentinel-rule.png" alt="Describe what the screenshot shows">` inside the
  card's details. Always write a meaningful `alt` description, and blur any IP addresses, usernames
  or lab credentials first.

### Add your resume

Save a public version of your resume (no phone number, home address or date of birth) as
`assets/resume/resume.pdf`. Then find `RESUME` in `index.html` and remove the `<!--` and `-->` around the Resume button so it appears.

### Update social links and contact details

- Find `SOCIAL LINKS` for the buttons at the top, and `CONTACT DETAILS` for the Contact section.
- Replace `[EMAIL]` with a link, for example `<a href="mailto:you@example.com">you@example.com</a>`.
- Replace `[TRYHACKME-PROFILE]` with your TryHackMe public profile link.
- External links should keep `target="_blank" rel="noopener noreferrer"` for safety.
- Do not add your phone number or home address.

## Publish it for free

Any static host works. Two easy options:

**GitHub Pages**
1. Create a new public repository on GitHub, for example `portfolio`.
2. Upload everything inside the `portfolio` folder (so `index.html` is at the top level).
3. In the repository, go to **Settings → Pages**, choose **Deploy from a branch**, pick `main` and `/ (root)`.
4. After a minute your site is live at `https://<your-username>.github.io/portfolio/`.

**Netlify**
1. Sign in at netlify.com and choose **Add new site → Deploy manually**.
2. Drag the `portfolio` folder onto the page.

After publishing, open `index.html` and update the `SEO` block: set `og:url` to your live address, and
set `og:image` to the full address of the image, for example
`https://<your-username>.github.io/portfolio/assets/og-image.png`.

## Security notes

- A Content Security Policy in `index.html` only allows files from this site to load. If you ever add
  an embedded video or external image, you will need to update that policy line.
- No forms, cookies, analytics or third-party scripts are used.
