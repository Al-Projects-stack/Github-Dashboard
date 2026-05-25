# GitScope - GitHub Analytics Dashboard
<img width="1872" height="921" alt="image" src="https://github.com/user-attachments/assets/471bc596-1293-4dc2-a76d-227c5188795a" />

A client-side GitHub profile dashboard. Enter any username and instantly see their repos, stars, forks, top languages, and best repositories all pulled live from the GitHub public API with no backend.

**Live:** https://github-dashboard-jbpu.onrender.com

---

## What it does

- Search any public GitHub username
- Displays follower/following counts, total stars, and repo count
- Language distribution chart (by repository count)
- Top repositories sorted by stars with descriptions and metadata
- Rate limit awareness shows when limits reset

## How it works

No backend. The browser sends `fetch()` requests directly to two public GitHub API endpoints:

```
https://api.github.com/users/{username}
https://api.github.com/users/{username}/repos
```

JavaScript processes the JSON response sums stars, counts languages, sorts repos and renders the UI. No server required for public profile data.

## Running locally

Open `index.html` in any browser with an internet connection. No build step, no dependencies.

```bash
# Or serve it locally
npx serve .
```

## Stack

- HTML / CSS / Vanilla JavaScript
- GitHub REST API v3 (public endpoints)
- No libraries, no frameworks, no backend

## Rate limits

GitHub allows 60 unauthenticated API requests per hour per IP. More than enough for a portfolio project. The dashboard displays an error with the reset time if the limit is hit.

## Deploy

Deployed as a static site on Render via `render.yaml`. Any static host (Netlify, Vercel, GitHub Pages) works too just serve `index.html`.
