# Warbell — landing page + releases

Public site and download host for **Warbell**, a Bevy 0.18 / Rust game where a knight
defends a central keep against night-wave ork sieges across a five-biome island.

- **Play it:** https://miskibin.github.io/warbell-game/
- **Download (Windows):** see [Releases](https://github.com/miskibin/warbell-game/releases/latest)

The game's **source code is private**. This repo holds only the public landing page
(`index.html`, served via GitHub Pages) and the release binaries (GitHub Releases).

## Releasing a new build

From the private source repo, build and package, then upload here:

```powershell
# in the source repo
cargo build --release

# stage warbell.exe + assets/ into a folder and zip it as warbell-windows.zip
# (see promo/ tooling), then from this repo:
gh release create v0.X.0 warbell-windows.zip `
  --repo miskibin/warbell-game `
  --title "Warbell v0.X.0" `
  --notes "Release notes here."
```

The download button on the page always points at
`releases/latest/download/warbell-windows.zip`, so a new release with that asset name
updates the site automatically — no HTML change needed.
