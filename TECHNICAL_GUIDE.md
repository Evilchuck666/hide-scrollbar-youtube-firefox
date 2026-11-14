# Hide-Scrollbar-YouTube technical guide

[Back to the project overview](README.md)

Hide-Scrollbar-YouTube is a Firefox WebExtension made of a manifest, one
content script and its icons. It needs no build step.

## Development

The add-on source lives in [`src/`](src):

| File | Purpose |
| --- | --- |
| `manifest.json` | Add-on metadata and the content script that runs on video pages. |
| `hide_scrollbar_youtube.js` | Injects the CSS rule that hides the scrollbar. |
| `icons/` | Add-on icons. |

With [Node.js](https://nodejs.org/) 20 or newer, from the repository root:

```sh
npx web-ext lint --source-dir src    # check the add-on
npx web-ext run --source-dir src     # try it in a temporary Firefox profile
npx web-ext build --source-dir src   # build an unsigned package
```

You can also load it by hand from `about:debugging` → **This Firefox** →
**Load Temporary Add-on…** and selecting `src/manifest.json`.

## Releases

Releases are built by the [`Build extension`](.github/workflows/release.yaml)
workflow. Every push and pull request lints the add-on and builds an unsigned
package. To publish a release:

1. Add the repository secrets `AMO_JWT_ISSUER` and `AMO_JWT_SECRET` with your
   [addons.mozilla.org API keys](https://addons.mozilla.org/developers/addon/api/key/)
   (only needed once).
2. Bump `version` in `src/manifest.json` and push it to `main`.
3. Go to **Actions → Build extension → Run workflow**, choose `main` and enter
   the same version (e.g. `1.2.0`, without the `v`).

The workflow signs the add-on on addons.mozilla.org as an unlisted add-on,
creates the `v<version>` tag and publishes a GitHub release with
`hide-scrollbar-youtube.xpi` and `SHA256SUMS.txt`.
