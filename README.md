## Local development

`bun dev` serves the Astro frontend locally against the **live** instance — no
local backend. It pulls the site's content snapshot with the frontend API token,
then runs `astro dev` from it (http://localhost:4321).

```sh
cp .env.example .env   # fill in EMDASH_API_TOKEN
bun install
bun dev
```

A site admin gets the token (and the ready-made `env` block) from
`https://premium-cms.com/_emdash/api/settings/frontend-token` while signed in; rotate it there
too. It reads content, schema and the snapshot (drafts included) and nothing
else — still, treat it like a password and never commit `.env`. Re-run
`bun dev` to pick up new content; `EMDASH_INCLUDE_DRAFTS=1 bun dev` includes
drafts.
