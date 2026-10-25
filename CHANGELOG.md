# Changelog

All notable changes to Kora Soplos Icons are documented in this file.

## [1.0.0-4] - not yet published

### Changed
- Changed icon utilities-system-monitor.svg from green to orange soplos

## [1.0.0-3] - 2026-10-25

### Added

- README: version, license, platform, format and package badges, as in the other Soplos projects.
- README: installation instructions for the `.deb` package, which is published in the Releases of the repository. It explains how to download it, how to install it with `apt` on any Debian based distribution, how to select the theme in Plasma, GNOME and Xfce, and how to remove it.

### Changed

- The session and power icons (`system-shutdown`, `system-reboot`, `system-suspend`, `system-hibernate`, `system-lock-screen`, `system-log-out` and `system-switch-user`) have a new circle behind the symbol, so the orange symbol is clearly visible at panel size, for example in the login and lock screens of Plasma. In the dark theme the circle is charcoal (`#1b1b1e` to `#3a3a40`) with a symbol from `#ff7d2e` to `#ffb070`; in the light theme it is light gray (`#d4d4d9` to `#f2f2f4`) with a symbol from `#d9600f` to `#ff7d2e`.

## [1.0.0-2] - 2026-10-25

### Changed

- Package revision 2 of 1.0.0: the Debian package is rebuilt from the current state of the themes, with the version read from `DEBIAN/control` by the build script. The first release is `1.0.0`, without a revision.

## [1.0.0] - 2026-10-25

### Added

- First release. Two icon themes for Soplos Linux built on Kora: `kora-soplos-dark` and `kora-soplos-light`. Kora ships a single variant, so the dark and the light one are new. The dark theme inherits `breeze-dark,breeze,hicolor` and the light one `breeze,hicolor`, so any icon Kora does not draw falls back to a Breeze icon of the matching brightness.
- The light variant has its own symbolic icons and panel icons. In the dark theme the symbols are light gray (`#dfdfdf`); in the light theme they are dark (`#252527`, the dark color of the Soplos web), including the 264 icons of `panel/16`, `panel/22` and `panel/24`, which were still light gray and would have been almost invisible on a light panel.
- Soplos logo: `distributor-logo-soplos` and `start-here-soplos` in apps and `distributor-logo-soplos` in places. The generic `distributor-logo` now shows the Soplos logo too, so every place that asks for the distribution logo gets it.
- Soplos icon for Ghostty (`com.mitchellh.ghostty`, with `ghostty` as a link to it): the ghost with the orange and black outline of the Soplos terminal. Kora's own Ghostty icon, a blue tile, was replaced. The new one was redrawn as an SVG from the original PNG, measuring the strokes and the curves of the ghost, so it scales without losing quality.
- Icons that Kora did not have: `file-manager-orange`, `proton-mail`, `torzu` and `vita3k`.
- Debian package `kora-soplos-icons` 1.0.0, architecture `all`, so the same `.deb` installs on Boro, Tyson and Tyron. It installs both themes in `/usr/share/icons`, depends on `hicolor-icon-theme` and recommends `breeze-icon-theme`, the theme they inherit from. The icon caches are not shipped: `postinst` generates them with `gtk-update-icon-cache` and `postrm` removes them, as a file created at install time cannot belong to the package. The packaging files are in `kora-soplos-icons/` and the build script, `kora-soplos-icons.sh`, is not part of the repository.
- README with preview screenshots of both themes (`screenshots/`), `AUTHORS` and `LICENSE` (GPL-3, the license of Kora). `CHANGELOG.md` and `README.md` are installed in `/usr/share/doc/kora-soplos-icons/`.

### Changed

- The accent color of Kora, blue (`#4285f4`), is replaced by the orange of Soplos (`#ff7d2e`) in more than 5,800 icons per theme, and the other colors come from the palette of the web (`#fec431`, `#252527`). The folders, which Kora draws with an inline `rgb()` color instead of a hexadecimal one, changed from blue to the red-orange `rgb(199,60,24)`. The four `disk-quota` status icons keep their blue on purpose.
- The cyan gradient that Kora uses in many generic app icons (calendar, camera, search, USB and others) is now an orange gradient. It was three colors repeated across 187 icons per theme: `#13bee3` became `#ff7d2e`, `#20ccff` and `#3dc0f9` became `#ff9a4d`, `#006783` became `#a04a12` and `#003251` became `#5c280a`. `update-low` wrote the same colors as `rgb()` and was changed by hand.
- The session and power icons of apps (`system-shutdown`, `system-reboot`, `system-suspend`, `system-hibernate`, `system-lock-screen`, `system-log-out` and `system-switch-user`), shown for example in the login and lock screens of Plasma, kept the navy blue gradient of Kora on their symbol. It is now orange. The gray-blue circle of Kora behind the symbol made the orange almost invisible at panel size, so the circle changed too: in the dark theme it is charcoal (`#1b1b1e` to `#3a3a40`) with a symbol from `#ff7d2e` to `#ffb070`, and in the light theme it is light gray (`#d4d4d9` to `#f2f2f4`) with a symbol from `#d9600f` to `#ff7d2e`.
- The blue of Kora in the system icons is now Soplos orange, in 81 icons per theme: the status icons (`ac-adapter`, `avatar-default`, `dialog-information`, `dialog-question`, `non-starred`, `image-missing`, the charging batteries, the `notification-*`, `package-installed-*` and `state_*` icons, among others), some actions, mimetypes and places, and the apps that belong to the system (`accessories-*`, `calendar`, `help-info`, `network-manager`, `scanner`, `gnome-disks`, `gnome-software`, the Plasma applets and the Xfce panel and session, among others). The hue of every blue in these files was turned to the hue of `#ff7d2e`, keeping its saturation and brightness, so the gradients stay as they were.
- The icons that stay blue on purpose are the weather icons (water and night), Bluetooth, KDE Connect, the disk quota icons and the logos of other distributions and applications.
- The colors of third-party logos (Gmail, Android Studio, Telegram and the like) are not touched, since they are the brand of each app. Other blues of Kora remain in app icons, none in more than 44 files each.
- `siyuan-note` is now `siyuan`.
- Every comment inside an SVG file is now in English. The Soplos logo and the Ghostty icon had their comments in Spanish.
- `icon-theme.cache` is regenerated for both themes after all the changes above.

### Fixed

- Fourteen links inherited from Kora had names that no application can ask for, with a double dot before the extension (the twelve `xsi-format-*-symbolic..svg` icons and `snap.telegram-desktop..svg`) or a double extension (`view-calendar-year.svg.svg`). Nothing pointed to them, so they are removed.
- `io.gitlab.adhami3310.Converter.svg.svg` was a real icon with a duplicated extension, so it could not be found by the name of the app. It is now `io.gitlab.adhami3310.Converter.svg`.
- Removed `Image application-x-drawy.svg`: a space in a file name breaks `gtk-update-icon-cache`, which is why Kora's own cache script warns about it.
- Neither theme has a broken symbolic link now.

### Credits

- Based on the Kora icon theme and its contributors: https://github.com/bikass/kora
- Soplos modifications by Sergi Perich. Project promoted by Simnandez.
