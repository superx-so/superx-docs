# superx-docs

Source for the SuperX public API documentation site (docs.superx.so), rendered by Mintlify.

- `docs.json` - site config (tabs, navigation, colors)
- `*.mdx` - documentation pages
- `api-reference/openapi.yaml` - OpenAPI 3.1 spec for the /v1 API; Mintlify generates the per-endpoint reference and try-it playground from it

Keep `openapi.yaml` in sync with the server: any change to a /v1 endpoint ships with the matching spec change.

## One-time setup (Rob)

1. Create a GitHub repo named `superx-docs` (public is fine) and push this folder's contents to it as the repo root.
2. Sign up at mintlify.com (free Hobby plan) with the GitHub account.
3. In the Mintlify dashboard, install the Mintlify GitHub app and connect the `superx-docs` repo. It auto-deploys on every push.
4. Set the custom domain to `docs.superx.so` in the dashboard, then add the CNAME record the dashboard shows in Cloudflare DNS.
5. Verify the site renders, the API Reference tab shows the playground, and that appending `.md` to any page URL (for example `https://docs.superx.so/introduction.md`) returns raw markdown.
6. Logo and favicon: none are committed yet. Add `logo` (light/dark) and `favicon` files to the repo and reference them in `docs.json`, or upload them in the Mintlify dashboard.

## Local preview

`npx mint dev` in this directory (needs a network fetch for the CLI; run when appropriate).
