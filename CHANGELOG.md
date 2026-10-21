# Changelog

All notable changes to Stack are documented in this file. Each version that is published also appears on the [Releases](https://github.com/Guayaba7/stack/releases) page with the same notes.

Version numbers follow the `MAJOR.MINOR.PATCH-STAGE` scheme. During the beta stage, only the last number increases with each published update.

## [0.6.2-beta] - 2026-10-21

This update changes how Stack is built and distributed. The program is now compiled to native machine code, and neither the installer nor the update packages contain the program's source code.

### Changed
- **Native compilation.** Stack is now compiled with Nuitka instead of being packaged with PyInstaller. The program and its store modules are translated to C and compiled into native Windows binaries, which protects the source code and may shorten start-up time.
- **Compiled update packages.** Lightweight updates (`codigo-x.y.z.zip`) now contain compiled modules instead of source files. Stack verifies that each module was built for its own runtime before installing it.
- **One-time full update.** Because the program's runtime has changed, computers running version 0.6.1 or earlier receive this version through the complete installer. Later versions return to lightweight updates.

### Fixed
- If a lightweight update cannot be loaded, Stack no longer attempts the same lightweight update again; it uses the complete installer instead.

## [0.6.1-beta] - 2026-10-21

This update introduces lightweight updates, fixes missing Hareruya prices in installed copies of Stack and makes the first data download visible on the loading screen.

### Fixed
- **Hareruya prices were not displayed in installed copies.** The Hareruya module looked for its files next to the program instead of in the user's data folder, so the HAR and HAR JP columns appeared empty even though the data had been downloaded correctly. Stack now directs the module to the user's data folder in all cases.
- **The loading screen appeared frozen at 0% during the first start.** On a new computer, Stack downloads approximately 62 MB of price history from the cloud. The progress bar now advances during the download, and the screen shows which file is being downloaded and how many megabytes have been received.

### Changed
- **Installer appearance.** The welcome and completion pages now match Stack's loading screen: the STACK title, the subtitle and the installer status are shown across the full width of the window, with text in a terminal typeface.
- **Installer language.** The installer is now available in English and Spanish and selects the language of Windows automatically.
- **Publisher name.** Windows now lists the publisher as "López. M" under installed applications.

### Added
- **Lightweight updates.** Starting with this version, an update downloads only the program code (approximately 300 KB) instead of the complete installer. Stack verifies the integrity of the package, checks that every component it requires is already present on the computer, and restarts with the new version within seconds. When a new version requires additional components, Stack downloads and runs the complete installer automatically, as before. If a lightweight update cannot be loaded for any reason, Stack starts with the previously installed version.
- Each published version now includes a code package (`codigo-x.y.z.zip`) in addition to the installer.
- The application log (`stack_log.txt`) now records the size of each cloud download and each completed file, to make connection problems easier to diagnose, as well as which version of the code is running.

## [0.6.0-beta] - 2026-10-21

First public beta of Stack, distributed through an installer and updated automatically.

### Added
- **Installer for Windows 10 and 11.** Stack can be installed on any computer without Python or additional components. The installer does not require administrator rights and downloads Microsoft WebView2 if it is not present.
- **Automatic updates.** On each start, Stack checks this repository for a newer version. When one is available, an **↑** button appears in the lower-left corner; two clicks download the new version, verify its integrity, install it and restart Stack. Purchases, inventories and settings are preserved.
- **Cloud price data.** Prices from Scryfall (TCGplayer), MTGJSON, Hareruya, StarCityGames and Card Kingdom are collected every morning and published automatically. Stack downloads only the files that changed since the previous start; users no longer need to run any downloads themselves.
- **Search in Analysis.** Every Analysis view (Movers, New, Watchlist, Arbitrage and Stock) can now be filtered by card name by typing directly in the view.
- **Card Kingdom buylist** in the charts, and profit amounts in the Arbitrage view according to the selected buying and selling stores.

### Changed
- User data (purchases, inventories, settings and downloaded prices) is stored in `%LOCALAPPDATA%\Stack\data`, separately from the program. Updating or uninstalling Stack does not remove it.
- Large data transfers between Stack's engine and its window are now sent in parts, which prevents the window from becoming unresponsive while loading.
- Problem reports are sent directly by e-mail, including a screenshot of the window and the relevant card data.

### Fixed
- The card details panel no longer fails with an internal error.
- Screenshots attached to problem reports are captured correctly on 64-bit Windows.
