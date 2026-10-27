# 🙈 Hide-Scrollbar-YouTube

**Watch YouTube without a scrollbar in the way.**

Hide-Scrollbar-YouTube is a tiny Firefox add-on that hides the page scrollbar
on YouTube video pages. The page still scrolls with the mouse wheel, touchpad
or keyboard; only the bar is gone, so the player and the page use the full
width of the window.

## ✨ What it does

- Runs only on YouTube video pages (`youtube.com/watch…`).
- Hides the scrollbar with a single CSS rule (`scrollbar-width: none`).
- Keeps scrolling working exactly as before.
- Needs no permissions, collects no data and has no settings.

## 📥 Download

| Browser | Latest stable release |
| --- | --- |
| Firefox 140+ | [Download](https://github.com/Evilchuck666/hide-scrollbar-youtube-firefox/releases/latest/download/hide-scrollbar-youtube.xpi) |

[Release notes](https://github.com/Evilchuck666/hide-scrollbar-youtube-firefox/releases/latest)

## 🚀 Getting started

1. Open the download link above in Firefox.
2. Accept the installation prompt.
3. Open any YouTube video: the scrollbar is gone.

To remove it, go to `about:addons` and uninstall **Hide-Scrollbar-YouTube**.

The `.xpi` published in each release is signed by Mozilla, so it installs in
regular Firefox builds. Firefox updates it only when you install a newer release.

## 🧠 Notes

- YouTube switches pages without reloading. If you open a video from the home
  page or search results, the scrollbar may stay until you reload the video
  page. Once hidden, it stays hidden on other YouTube pages in that tab until
  the next reload.

## 🛠️ Development

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

## 📦 Releases

Releases are built by the [`Build extension`](.github/workflows/build.yml)
workflow. Every push and pull request lints the add-on and builds an unsigned
package. To publish a release:

1. Add the repository secrets `AMO_JWT_ISSUER` and `AMO_JWT_SECRET` with your
   [addons.mozilla.org API keys](https://addons.mozilla.org/developers/addon/api/key/)
   (only needed once).
2. Bump `version` in `src/manifest.json` and push it to `main`.
3. Go to **Actions → Build extension → Run workflow**, choose `main` and enter
   the same version (e.g. `1.1.0`, without the `v`).

The workflow signs the add-on on addons.mozilla.org as an unlisted add-on,
creates the `v<version>` tag and publishes a GitHub release with
`hide-scrollbar-youtube.xpi` and `SHA256SUMS.txt`.

## 📜 License

Released into the public domain under [The Unlicense](LICENSE).
