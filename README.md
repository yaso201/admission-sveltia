# admission-sveltia — Sveltia CMS Auth (Cloudflare Worker)

Backend OAuth GitHub pour le CMS Sveltia de LaNEM (applicant `/admin` + vitrine).
Code : worker officiel [`sveltia/sveltia-cms-auth`](https://github.com/sveltia/sveltia-cms-auth).

## Déploiement
Connecté à Cloudflare Workers via « Continue with GitHub » → redéploie à chaque push.

## Variables (dashboard Worker → Settings → Variables and Secrets)
- `ALLOWED_DOMAINS` = `admissions.lanem.bj` (dans wrangler.toml ; chaque hôte qui sert `/admin/`, jamais de joker — D-SEC-CMSAUTH-02)
- `GITHUB_CLIENT_ID` — **secret** (GitHub OAuth App)
- `GITHUB_CLIENT_SECRET` — **secret** (GitHub OAuth App)

## Côté CMS
`config.yml` → `backend.base_url: https://<worker>.workers.dev`
GitHub OAuth App → Authorization callback URL : `https://<worker>.workers.dev/callback`
