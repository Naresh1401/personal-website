# 🌐 Naresh Sampangi — Personal Portfolio Website

![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-Deployed-222?logo=github)
![CI/CD](https://img.shields.io/badge/CI/CD-GitHub_Actions-2088FF?logo=githubactions&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)

Enhanced personal portfolio website with **automated deployment** and **repository monitoring**. Showcases expertise in Generative AI, LLM Engineering, and Data Science.

---

## Features

- Animated aurora hero with a live "agent console", glass nav and light/dark themes
- Responsive project gallery with category filters, headline metrics and live demo links
- Live GitHub stats, languages, activity and latest repos (cached to stay under the API rate limit)
- Automated GitHub Pages deployment via GitHub Actions
- **Daily repo monitor** — automatically detects new repos and creates GitHub issues suggesting portfolio additions

## CI/CD Workflows

| Workflow | Trigger | Purpose |
|----------|---------|---------|
| `deploy.yml` | Push/PR to `main` | Lints HTML/CSS (`validate` job), then deploys to GitHub Pages on push (PRs only run validation) |
| `check-new-repos.yml` | Daily cron (9 AM UTC) | Detects new repos, opens a PR to update `.known_repos` for manual review/merge, and files an issue |

## Local Development

Requires Node.js 18+.

```bash
npm install       # install dev tooling (one-time)
npm run serve     # preview the site at http://localhost:8080
npm run lint      # lint HTML (html-validate) and inline CSS (stylelint)
```

Run `npm run lint` before pushing — the same check runs in CI and blocks deployment if it fails.

## Tech Stack

- **HTML5** + **CSS3** (mesh gradients, custom properties)
- **JavaScript** (vanilla)
- **Google Fonts**: Syne, Geist, Geist Mono
- **Icons**: inline SVG sprite from Lucide, Bootstrap Icons (GitHub/LinkedIn) and Simple Icons (ORCID)
- **GSAP + ScrollTrigger** and **Lenis** for scroll motion and smooth scrolling (CDN, with SRI)
- **cobe** (globe) and **ninja-keys** (⌘K palette), self-hosted in `vendor/`
- **GitHub Actions** for CI/CD
- **GitHub Pages** for hosting

---

## Project Structure

```
personal-website/
├── index.html                          # Portfolio page
├── 404.html                            # Custom GitHub Pages 404
├── og-image.png                        # Social sharing preview image
├── vendor/                             # Self-hosted cobe + ninja-keys bundles
├── .known_repos                        # Tracked repos for change detection
├── package.json                        # Local lint/serve scripts
├── .stylelintrc.json / .htmlvalidate.json
└── .github/
    ├── dependabot.yml                  # Keeps GitHub Actions versions updated
    └── workflows/
        ├── deploy.yml                  # Lint + deploy to GitHub Pages
        └── check-new-repos.yml         # Daily new repo monitor (opens PR)
```

---

## Author

**Naresh Sampangi**
