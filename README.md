# pslm-releases

Public hosting for the **PSLM** desktop app's Sparkle auto-update feed.

- **Appcast:** served via GitHub Pages at
  `https://pslmsound.github.io/pslm-releases/appcast.xml`
  (this is the `SUFeedURL` baked into the app's `Info.plist`).
- **Release DMGs:** uploaded as assets on GitHub Releases (tag `vX.Y.Z`).

## Publishing a new version
1. In the app repo: `standalone/dist/release.sh <version>` (build → sign → DMG →
   notarize → staple → EdDSA-sign → prints the appcast `<item>`).
2. Create a GitHub Release here tagged `vX.Y.Z`; upload `PSLM-X.Y.Z.dmg`.
3. Paste the printed `<item>` at the **top** of `appcast.xml`, commit, push.
   GitHub Pages redeploys automatically.
