## Local development

`bun dev` serves the Astro frontend locally against the **live** instance — no
local backend, no snapshot file. `astro dev` live-connects the same way the
platform's builds and previews do: EmDash reads an in-memory database kept
fresh from the backend's `/_emdash/api/snapshot`, and `/_emdash/*` requests
are proxied to the backend (http://localhost:4321).

```sh
cp .env.example .env   # fill in EMDASH_API_TOKEN
bun install
bun dev
```

A site admin gets the token (and the ready-made `env` block) from
`https://premium-cms.com/_emdash/api/settings/frontend-token` while signed in; rotate it there
too. It reads content, schema and the snapshot (drafts included) and nothing
else — still, treat it like a password and never commit `.env`. Content is
live: publish in the admin and reload the page. `EMDASH_INCLUDE_DRAFTS=1
bun dev` renders drafts too.
