# Changelog

All notable changes to Stack are documented in this file. Each version that is published also appears on the [Releases](https://github.com/Guayaba7/stack/releases) page with the same notes.

Version numbers follow the `MAJOR.MINOR.PATCH-STAGE` scheme. During the beta stage, only the last number increases with each published update.

## [0.6.6-beta] - 2026-10-22

This update addresses start-up failures and records a report whenever Stack does not start or close correctly.

### Added
- **Automatic failure reports.** Stack now records the progress of each start. If Stack closes unexpectedly, stops responding while loading or is closed before it finishes loading, the next start saves a report in the `fallos` folder inside the application data folder. The report includes the loading step that was reached, the session log, and the state of the program at the time of a crash or freeze. Stack shows a notice when a new report has been saved. The 30 most recent reports are kept.

### Fixed
- **Start-up could remain on "looking for new data" indefinitely.** The connection to the cloud now has a total time limit of 45 seconds. If the cloud does not respond within that time, Stack continues with the data already saved on the computer instead of waiting.
- The loading screen now shows "LOADING…" when the interface is in English.

## [0.6.5-beta] - 2026-10-22

This update adds an English interface.

### Added
- **Language selection.** Stack can now be used in English or Spanish. The language is chosen in Settings › Language, takes effect immediately and is remembered. On first start, Stack uses English unless Windows is set to Spanish.
- **English interface.** Menus, settings, screens, messages, tooltips, keyboard shortcut names and dates are shown in English. Card names, set names and card text are not translated, since they come from the price sources. Any text that does not yet have a translation is shown in Spanish.

## [0.6.4-beta] - 2026-10-21

This update keeps cards visible when the daily price source omits a price and adds a close button to every window.

### Added
- **Previous-day prices.** When Scryfall does not provide a price for a card version on a given day, Stack now uses the most recent price from the previous 14 days instead of omitting the card. These prices are marked with a dagger (†) in the Market list, the gallery, the card details and the card sheet; hovering over the mark shows the date of the price. Versions whose price fell below the catalog threshold are not affected and are excluded as before.
- **Close buttons.** Every window that opens over the main screen, such as Settings, Stores, Cart, Import, Report, Help and the price alert, now has a close button (✕) in its upper-right corner, in addition to the Esc key.

## [0.6.3-beta] - 2026-10-21

This update simplifies how store prices reach Stack, makes the purchase settings visible across the application and adds a help button.

### Changed
- **Stack opens on the Market tab.** Stack no longer opens the settings screen on start when the exchange rate or the purchase percentage is missing. A short notice explains where to set them instead.
- **Purchase settings are reflected in Market and Analysis.** The Movers, New entries and Watchlist views now show the amount you would pay for each card, calculated from the purchase percentage and limited by the minimum ROI and the minimum gross margin. Each view also summarizes the effective percentage, ROI and gross margin that result from your settings.
- **Arbitrage respects the minimum gross margin.** In addition to the minimum ROI, the arbitrage view now hides opportunities below the minimum gross margin set in Settings, and shows the margin of each opportunity.
- **Store prices are delivered only through the cloud.** Users no longer download store prices themselves, and the Ctrl+T shortcut has been removed. Clicking the store indicators at the bottom right of the window opens a panel that shows the date of each store's prices; its only action, SYNC, checks the cloud for newer data and downloads it. When new price history arrives, the panel offers to restart Stack to load it.
- **Settings › Reports opens the report form directly**, without an intermediate screen.

### Added
- **Hareruya availability.** Stack now indicates when Hareruya is not responding, for example during scheduled maintenance, both in the status bar and in the store panel. In that case Stack continues to use the most recent valid Hareruya prices.
- **Help button.** A new button marked with a question mark, next to the report button, links to the Stack wiki, which explains each screen, how offers, ROI and gross margin are calculated, where prices come from and every keyboard shortcut.

### Removed
- The Hareruya price source row in Settings › Price.

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
