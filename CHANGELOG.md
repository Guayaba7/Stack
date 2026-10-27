# Changelog

All notable changes to Stack are documented in this file. Each version that is published also appears on the [Releases](https://github.com/Guayaba7/stack/releases) page with the same notes.

Version numbers follow the `MAJOR.MINOR.PATCH-STAGE` scheme. During the beta stage, only the last number increases with each published update.

## [0.7.2-beta] - 2026-10-27

This update reorganizes Settings into three columns and adds a home page with the day's market movers and the articles published on the Stack website, which can now be read inside the application.

### Added
- **Home page.** Clicking the Stack logo in the upper-left corner opens a home page that is separate from the Market, Analysis, Inventory and History tabs. It shows:
  - **Movers:** a row of up to twelve cards with their image, the price change for the period, the printing and the current price. Tab switches between cards that went up and cards that went down, and Enter or a click opens the card details.
  - **Articles:** the articles published on the Stack website, with cover image, date, reading time and summary. The featured article is shown larger.
  - **Today:** the date of the prices, the exchange rate, the number of inventories and copies, the watchlist and its price alerts, and the account status, with shortcuts to the four tabs.
  Esc or any tab returns to the previous view. Typing closes the home page.
- **Article reader.** Articles open inside Stack with their images, tables, notes and card lists. Card names in an article are linked to their details in Stack and show the current price; card lists show the image and price of each card. Links to other websites open in the browser, and OPEN ON THE WEBSITE opens the article on the Stack website. The list of articles is kept on the computer, so it remains available without a connection; opening an article requires a connection.

### Changed
- **Settings in three columns.** Settings now opens on three groups: DATA (Price and Cloud), INTERFACE (Language, Video, Theme and Controls) and ACCOUNT (User and Reports). Choosing a group with Enter or a click shows its sections in the second column, and choosing a section shows its options in the third column, where they are edited as before. Each group and section has a short description, the path is shown in the title (for example SETTINGS › INTERFACE › THEME), and Left arrow or Esc goes back one column. The window now uses most of the screen, with larger spacing and text.

## [0.7.1-beta] - 2026-10-26

This update makes synchronization work in both directions, so cards added on the Stack website or on another computer now appear in the application. It also fixes copying the recovery code, redesigns the account window and adds the account to Settings.

### Added
- **Two-way synchronization.** Stack now also receives changes from the account, not only sends them. Inventories, the watchlist and the theme changed on the Stack website or on another computer are applied on this computer when Stack opens, every minute while it is open, before every upload and when SYNC NOW is used. Open views (Inventory, Watchlist) are refreshed and a notice shows how many copies changed.
- **The most recent save prevails.** Each inventory, the watchlist and the theme are compared separately. When the same item was changed in two places, the version saved last is kept. If two devices save at the same moment, the second one waits for the next cycle and the decision is made again, so no save is overwritten blindly.
- **Cards added from the website.** The Stack website can now add a card to any inventory of the account, with quantity and an optional cost per copy. Stack receives the new copies within a minute; the average cost is preserved.
- **Inventories created or deleted elsewhere.** An inventory created on another computer appears in Stack; one deleted on another computer is also removed here, unless it was changed here afterwards. The default inventory is never deleted.
- **Settings › User › Stack account.** Shows whether the computer is signed in, with the username and the last synchronization, and opens the account window with Enter.

### Changed
- **Redesigned account window.** Sign-in and account creation are two tabs in the same window, with one field per line, a highlighted main button and shorter texts. On start, Stack opens on Sign in if an account was used on the computer before, and on Create account otherwise. "Use without an account" remains available at the bottom.
- **Account actions.** The account window (Ctrl+U) shows the username and the time of the last synchronization, with three actions: CHANGE PASSWORD, RECOVERY CODE and SIGN OUT. Sync now remains available below them. RECOVERY CODE explains that the code cannot be shown again and creates a new one; the previous code stops working. When signed out, "Recover account" is available next to Sign in.
- **Password requirements shown while typing.** When creating an account, recovering it or changing the password, two indicators show whether the password has at least 10 characters and whether both entries match.
- **Joining data on first sign-in.** When a computer signs in to an account for the first time, inventories that exist on both sides with the same name, and the default inventories, are combined by adding their copies; the watchlists are combined. Items that exist only in the account are brought in, and items that exist only on the computer are uploaded. Previously, account data was brought in only when the computer had no data.
- The recovery code is shown on a single line.
- The "Username" entry in Settings › User is now named "Name on this computer" and explains that it is the name entered on the welcome screen, not the Stack account.

### Fixed
- **The COPY button did not copy the recovery code.** The Stack window does not allow web pages to write to the clipboard, so the button always reported that the code could not be copied. The code is now copied through the Windows clipboard.
- **Restoring factory settings while signed in.** Settings › User › Restore factory settings now signs out of the account before deleting local data. Previously, the empty watchlist and default settings left on the computer could have been uploaded to the account and replaced the saved copy.
- Stack no longer uploads the theme again on every start when it had been received from the account.

## [0.7.0-beta] - 2026-10-26

This update introduces Stack accounts. The theme, the watchlist and every inventory can now be saved to an account, shared with other computers and viewed on the Stack website. All data is encrypted on the computer before it is sent, so no one other than the account owner can read it, including the operators of Stack.

### Added
- **Sign-in on start.** When Stack opens, it asks for a Stack account before loading. Three options are available: sign in, create an account, or continue without an account, in which case Stack works exactly as before and all data remains on the computer. When "Remember on this computer" is selected, later starts sign in automatically; the saved session is protected with the user's Windows account and cannot be used from another Windows account or computer.
- **Account creation.** An account requires only a username and a password of at least 10 characters; no e-mail address is requested. Before the account is created, the user must confirm that the data cannot be recovered if both the password and the recovery code are lost.
- **Recovery code.** After the account is created, Stack shows a 25-character recovery code once. It can be copied or saved as a text file in the Documents folder, and the user must confirm that it has been saved before continuing. With the code, "I forgot my password" sets a new password and keeps all data; every other session is closed.
- **Automatic synchronization.** The theme (including the custom theme colors and the animation setting), the watchlist with its price alerts, and each inventory with its cards, quantities and average costs are uploaded a few seconds after every change, in the background and without interrupting work. Only the items that changed are uploaded. An inventory deleted on the computer is also removed from the account.
- **Theme shared with the website.** The theme selected in Stack is applied on the Stack website when signed in to the same account. Themes can only be chosen in the application. When a remembered session starts, Stack also applies a theme that was changed on another computer.
- **First sign-in on another computer.** When a computer without inventories or watchlist signs in, the inventories and the watchlist are brought from the account. A computer that already has data keeps it and adds it to the account.
- **Account window (Ctrl+U).** Shows the username and the time of the last synchronization, and offers SYNC NOW, CHANGE PASSWORD, NEW CODE (the previous recovery code stops working) and SIGN OUT. Signing out keeps all data on the computer. The shortcut can be changed in Settings like any other.

### Security
- The password, the recovery code and the data never leave the computer in readable form. The server receives only a hash of the username, a key derived from the password with PBKDF2-SHA256 (600,000 iterations) and documents encrypted with AES-256-GCM. Inventory names are stored only inside the encrypted documents.
- Changing the password or generating a new recovery code requires proof of the account key in addition to the session, so a stolen session cannot lock the owner out.
- After eight wrong passwords or recovery codes, the account is locked for 15 minutes.

### Changed
- Stack now requires the `cryptography` component, which is included in the installer.

## [0.6.7-beta] - 2026-10-23

This update adds card search in other languages, corrects Hareruya prices that were taken from products other than single cards and restores the session after a normal close.

### Added
- **Search in other languages.** The Market and Analysis search and the list import now also recognize the official card names in Spanish, French, German, Italian and Portuguese. For example, searching for "relampago" finds Lightning Bolt. Accents and capital letters are not required. The names are added with the next daily cloud update.

### Fixed
- **Hareruya prices from products that are not single cards.** Art Series cards, mini posters, Jumpstart theme cards and Vanguard cards are no longer matched to a card version. For example, Urza, Lord High Artificer (Modern Horizons) showed a Hareruya price of ¥30, which was the price of its Art Series card. Consignment items, artist proofs, signed, graded, inked and altered cards, and multi-copy sets are also excluded, since their prices do not represent a single near-mint copy sold by the store. Prices are corrected with the next daily cloud update.
- **Incomplete Hareruya matching on repeated cloud runs.** When the daily cloud update ran again on the same day, for example to retry Hareruya, the full Scryfall card index was not available. Card versions under $2 could not be recognized and some products were left unmatched. The index is now always available before Hareruya prices are matched.
- **The cart, search and filters were not restored after a normal close.** In version 0.6.6, the record used to detect failed starts was saved in the same file as the session, so closing Stack normally removed the session. The two are now stored separately.

### Changed
- **Language setting.** Settings › Language now shows its title and label only in the selected language.
- The store review tools show, for Hareruya and StarCityGames, the share of products matched against the 99% target, the number of ambiguous matches, which are listed first, and the reason for each product that needs review.

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
