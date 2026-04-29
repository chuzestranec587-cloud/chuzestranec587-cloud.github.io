# chuzestranec587 portfolio

Personal portfolio page for `chuzestranec587.is-a.dev`. Single static HTML file,
no build step, no JS dependencies — just open `index.html` in a browser.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The portfolio page itself. Edit content here. |
| `CNAME` | Tells GitHub Pages to serve this site at `chuzestranec587.is-a.dev`. **Do not edit.** |
| `is-a-dev_chuzestranec587.json` | Registration file for is-a-dev PR #1 (this domain). |
| `is-a-dev_solo-ai.chuzestranec587.json` | Registration file for is-a-dev PR #2 (project subdomain). |

## Deploy steps

### 1. Push to GitHub Pages

Create a public repo on GitHub named **exactly** `chuzestranec587-cloud.github.io`
(the username-based pattern is auto-published as Pages without any config):

```powershell
cd F:\solo_ai_html\portfolio_site
git init -b main
git add .
git commit -m "Initial portfolio"
git remote add origin https://github.com/chuzestranec587-cloud/chuzestranec587-cloud.github.io.git
git push -u origin main
```

GitHub will activate Pages automatically within a minute or two. Visit
`https://chuzestranec587-cloud.github.io` to confirm it loads.

> The `CNAME` file in the repo will point Pages to serve at
> `chuzestranec587.is-a.dev`. That domain won't resolve yet — that's fixed in
> step 2.

### 2. Submit is-a.dev PR #1 — `chuzestranec587.is-a.dev`

1. Fork [is-a-dev/register](https://github.com/is-a-dev/register).
2. In your fork, copy `is-a-dev_chuzestranec587.json` to
   `domains/chuzestranec587.json` (just the file rename, content stays).
3. Open a PR back to `is-a-dev/register:main`.
4. Fill the PR template — be specific that it's a **personal dev portfolio**
   (the previous one was rejected for being a project page, not a portfolio).
5. Wait for review (a few hours to ~3 days).

Once merged, give DNS ~10–15 minutes to propagate, then visit
`https://chuzestranec587.is-a.dev` to verify.

### 3. Submit is-a.dev PR #2 — `solo-ai.chuzestranec587.is-a.dev`

Only after PR #1 is merged and the portfolio is live:

1. In your same fork, copy `is-a-dev_solo-ai.chuzestranec587.json` to
   `domains/solo-ai.chuzestranec587.json`.
2. Open another PR.
3. Mention in the description that this is the **project subdomain** for
   Solo AI HTML, with the portfolio at `chuzestranec587.is-a.dev`.

### 4. Update Solo AI's `public_url`

Once `solo-ai.chuzestranec587.is-a.dev` is live, update
`smtp_config.json` in the Solo AI workspace:

```json
"public_url": "https://solo-ai.chuzestranec587.is-a.dev"
```

The mailer auto-reloads — no restart needed.

## Notes

- The portfolio is intentionally simple — it just needs to look like a real
  personal site (which it is) so the is-a.dev maintainers see clear dev focus.
- Update `index.html` whenever you want — every `git push` triggers a redeploy
  in ~30 seconds.
- All emails / GitHub URLs in the JSON files use `chuzestranec587-cloud`
  (your GitHub handle) and `chuzestranec587@gmail.com`. Change either before
  pushing if it's wrong.
