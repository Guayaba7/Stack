# Changelog

All notable changes to Stack are documented in this file. Each version that is published also appears on the [Releases](https://github.com/Guayaba7/stack/releases) page with the same notes.

Version numbers follow the `MAJOR.MINOR.PATCH-STAGE` scheme. During the beta stage, only the last number increases with each published update.

## [0.9.4-beta] - 2026-11-10

This update adds two animated themes, lets the deckbuilder search find cards by their name in other languages, puts the full card actions on the card shown in META and the DECKBUILDER, and makes the price ticker open the card in Market from any tab.

### Added
- **Black Hole theme.** A full-screen animated background drawn on the graphics card. Each pixel follows a ray of light that bends around the black hole, so the back of the accretion disk shows above and below it, and the side of the disk that turns toward the viewer is brighter. When matter falls in, a flare lights the disk and the application's accent changes from orange to white. The background is drawn at half resolution and scaled up to keep it light. If the computer cannot use WebGL, a simple gradient is shown instead.
- **Seigaiha theme.** The Japanese wave pattern in wine tones, drifting slowly to the side. A band of light crosses the pattern diagonally, and while it passes over the list the accent becomes lighter.
- **Card actions in META and the DECKBUILDER.** The card shown in the right panel now has the same buttons as Market: VIEW FULL SHEET (Ctrl+I), ADD TO WATCHLIST (Ctrl+D), compare, price alert and report. They act on the printing used in the deck, or on the cheapest printing when the deck does not specify one. The keyboard shortcuts now act on this card in both tabs.

### Changed
- **Deckbuilder search in other languages.** The deckbuilder search, including the commander search, now finds cards by their name in other languages, as Market does. For example, "relampago" finds Lightning Bolt. Results that match the full name in any language are listed first.

### Fixed
- **Price ticker.** Clicking a card in the ticker opened Market with its details only when Collection was open. It now does so from every tab, including META and the DECKBUILDER.
- **Keyboard shortcuts in META and the DECKBUILDER.** Ctrl+I and Ctrl+D acted on the last card selected in Market rather than on the card shown in the right panel.

## [0.9.3-beta] - 2026-11-09

This update adds a gallery view to binders, gives the Parchment theme its own typeface and makes the colors of the META archetype tiles match the deck shown in the details.

### Added
- **Binder gallery view.** A binder's stock can now be shown as a gallery of card images, as in Market. Each image shows the number of copies, the finish, today's market price and the difference against what was paid. The LIST / GALLERY selector is in the binder bar, Ctrl+G switches between them, and the choice is remembered. In the gallery, the arrow keys move by card and by row, and multiple selection (Ctrl+click) marks cards with an amber border.

### Changed
- **Parchment theme typeface.** The theme now uses a serif typeface (Palatino Linotype, with Book Antiqua and Georgia as alternatives), with lining, evenly spaced numbers so that prices stay aligned. Tab names and titles use small capitals. The same typeface applies on the Stack website.

### Fixed
- **META archetype tile colors.** The colors on an archetype tile now come from the same deck list shown in the details panel. Before, they came from every card played in that archetype, so a tile could show colors that the displayed deck does not use.
- **Retro Sunset theme.** The stripes on the sun no longer jump back to the top or extend past its edge. They now stay inside the sun and move down smoothly, getting thicker as they go.
- **Right panel.** When switching between COLLECTION, META and the DECKBUILDER, the right panel no longer keeps the details of the previous tab.
## [0.9.2-beta] - 2026-11-09

This update merges Inventory and Collection into a single COLLECTION tab with a portfolio chart. It also adds ten new themes, changes the CRT theme to white phosphor and fixes the deck panel moving when a deck is selected.

### Added
- **Nine new full-screen animated themes**, drawn behind the whole interface like Plasma, Grid Shift, Contour and Galaxy:
  - **Flow:** thousands of particles that follow colored currents and leave fading trails.
  - **Circuit:** copper circuit traces with cyan light pulses that travel along them.
  - **Lava lamp:** large magenta and orange blobs that rise, sink and merge.
  - **Constellation:** drifting stars that join with golden lines when they come close.
  - **Embers:** sparks that rise from a fire at the bottom of the screen and flicker out.
  - **Pool floor:** cyan light reflections moving like the floor of a swimming pool.
  - **Digital rain:** columns of mana symbols and characters that fall in ice blue.
  - **Retro sunset:** a striped sun behind mountains and palm trees. As in Galaxy, the card names and titles cycle through the sunset colors, each row slightly offset.
  - **Mana cycle:** every few seconds one mana color (white, blue, black, red or green) dominates the background, and the accent, borders and selection of the whole interface take on that color.
- **Parchment theme.** A light sepia theme, like an old-border card, without animation.
- Each new theme has its own animated preview in the theme list. All of them also apply on the Stack website.
- **Portfolio chart.** The COLLECTION tab opens with a chart of the combined value of all binders over time. It has the same periods (7D, 30D, 90D, all) and modes (actual history, or today's holdings at each day's prices) as the inventory chart, and shows what was paid.
- **VIEW CHART button** in the binder details, which opens that binder directly in its value chart.

### Changed
- **One COLLECTION tab.** Inventory and Collection are now a single COLLECTION tab, which takes the place of INVENTORY and its F7 shortcut. The separate COLLECTION tab and its Ctrl+5 shortcut were removed.
  - The tab opens with the portfolio chart, the binders (inventories) and the decks.
  - Opening a binder shows the usual inventory view, which now has a ‹ COLLECTION button (or Backspace) to return.
  - Clicking the COLLECTION tab or pressing F7 always returns to the portfolio.
- **CRT theme.** It now uses a cold white phosphor instead of green, so it no longer resembles the default green theme.
- **Binder tiles.** The tiles in COLLECTION show the difference against the purchase cost on its own line, so the values no longer overflow.

### Fixed
- **DECKBUILDER.** When a panel had been resized, selecting a deck of a different format moved the whole search area, because the SEARCH / EDHREC selector appeared only for Commander and changed the height of the filter rows. The selector now always keeps its place (hidden outside Commander), so the area no longer moves.
- **META.** Moving the selection no longer redraws the whole list. Card images no longer flicker or jump when a deck is selected.
## [0.9.1-beta] - 2026-11-09

This update reorganizes the DECKBUILDER and adds an Arena-style gallery to it. It also adds a COLLECTION tab, archetype tiles in META and the CRT theme. A custom theme can now take its colors from its background image.

### Added
- **COLLECTION tab (Ctrl+5).** Binders (inventories) and saved decks are shown separately, each as a tile.
  - A binder tile shows its most valuable card, the number of copies and cards, its market value and the difference against its cost.
  - A deck tile shows its commander or its most expensive card, its format, color identity, card count, TCG price, the share of the deck already owned and any legality problems.
  - Selecting a tile shows its details in the right panel. Double click or Enter opens it in INVENTORY or in the DECKBUILDER. New binders and decks can be created from this tab.
- **DECKBUILDER gallery view (Ctrl+G).** It is a view in the style of MTG Arena.
  - Search results are shown as compact card images. Each image shows the number of copies already in the deck, the price and the copies owned.
  - The deck is shown below in columns by mana value, plus columns for lands, sideboard and maybe. Each card appears as a strip with its art, cost and +/− controls, and the commander is shown as an image.
  - The choice between list and gallery is remembered.
- **Card printings.** Clicking a card in the gallery, or pressing Space on a selected card, opens all of its printings with images and TCG and Card Kingdom prices. Choosing a printing sets it as the deck version, and the card can be added to the main deck, the sideboard or as the commander from the same view.
- **META archetype tiles.** Archetypes and commanders are shown as tiles in the style of MTGGoldfish. Each tile shows the art of a signature card, the colors, the meta share and trend, the deck price and the cost of the missing cards. The signature card is the archetype's key card when MTGGoldfish provides one; otherwise, it is the card most characteristic of that archetype. The table view remains available (Ctrl+G).
- **CRT theme.** It reproduces an old green phosphor monitor, with scan lines, a slow sweep and a slight flicker. Its preview in the theme list is animated. It also applies on the Stack website.
- **Colors from the background image.** The custom theme has a new MATCH THE IMAGE option. It takes the base tone and the two most vivid colors of the background image and turns them into a readable palette. On the website and on the phone, the custom theme continues to apply its colors only, without the image.

### Changed
- The top tabs show only their names. The keyboard shortcut of each tab appears in its tooltip.
- The empty card image no longer shows a message when no card is selected.
- **DECKBUILDER filters.** They now use the same icons as Inventory: the color symbols, the type icons (including planeswalker and battle) and the rarity icons, with a button to clear them. The mana value filter is a boxed selector, and the filters are arranged in two rows.
- **EDHREC in the DECKBUILDER.** The EDHREC option appears only for Commander-style formats. The filters also apply to the EDHREC recommendations.
- **DECKBUILDER and META buttons.** The DECKBUILDER actions (new, delete, import, copy list, duplicate, share) and the META format buttons use the same framed button style as Inventory.
- **Deck list.** It is now organized as a table with column headers, a card count and subtotal per group, alternating row shading and the price of each line. The deck summary shows the store totals as a selector and groups the budget price, missing cards, curve and colors in separate rows.
- **Resizable deck panels.** The deck panel in the DECKBUILDER and in META can be resized by dragging its border, like the other panels. In the gallery view, the height of the deck area can be adjusted. Double click restores the original size.
- The search list is more compact, with the copies already in the deck and a rarity icon on each row.

### Fixed
- The color counts of the deck summary were displayed with an incorrect layout because two styles shared the same name.

## [0.9.0-beta] - 2026-11-08

This update adds two new tabs, META and DECKBUILDER. META shows which decks and cards are being played in each format, collected every day from several tournament sites. DECKBUILDER builds and edits decks with Stack prices, EDHREC recommendations for Commander and automatic legality checks. Decks are saved encrypted in the Stack account and can also be opened on the Stack website.

### Added
- **META tab (Ctrl+3).** It covers Standard, Pioneer, Modern, Legacy, Pauper, Commander and cEDH, with the decks of the last 21 days. The data is collected every day in the cloud from MTGO, MTGTop8, MTGGoldfish, TopDeck.gg and EDHREC. Each deck is classified into an archetype by comparing its cards with the typical list of each known archetype. The tab has the following views:
  - **Archetypes:** the share of each archetype, its trend against the previous week, its colors and the price of a typical list.
  - **Decks:** every recorded deck with its event, date, place and player.
  - **Staples:** the cards that appear in the most decks of the format, with their average number of copies.
  - **Thermometer:** the cards whose presence in the meta is rising or falling the most.
  - **Alerts:** cards from the user's inventories that enter or leave the meta, or that change legality (for example, a ban).
  - **Commanders:** in Commander and cEDH, the most played commanders and pairs, with their number of decks and trend.
- **Deck panel.** Selecting a deck in META shows its list grouped by card type, with the following:
  - its total price at TCG, Card Kingdom, StarCityGames and Hareruya;
  - a budget version that uses the cheapest printing of each card at any store;
  - the cards missing from the user's inventories and their cost, which COPY can send to IMPORT LIST in Market or to a store.
- **Copy to DECKBUILDER.** Enter, or the COPY TO DECKBUILDER button, saves any META deck as a new deck of the user.
- **DECKBUILDER tab (Ctrl+4).** It is an MTGO-style editor, with the card search on the left and the deck on the right.
  - The search filters by name, type, color and format, and shows only cards that are legal in the selected format.
  - The zones are main, sideboard, commander and maybe. Enter adds a card to the main deck, Shift+Enter to the sideboard, Alt+Enter to maybe and Ctrl+Enter sets it as the commander.
  - In Commander and cEDH, setting the commander automatically marks its color identity, and the search then shows only cards inside that identity.
  - Each card shows its legality in every format and its available printings with TCG and Card Kingdom prices. A printing can be chosen for the deck.
  - The deck is checked continuously for the following problems, which are listed under the deck:
    - cards that are not legal or are banned in the format;
    - more copies than allowed;
    - too few cards;
    - a missing commander;
    - cards outside the commander's identity.
  - Commander decks show an estimated bracket based on the number of Game Changers they contain.
  - Decks can be duplicated, deleted, copied as an MTGO or Arena list, or imported from a pasted list in MTGO, Arena, Moxfield or Archidekt format.
- **EDHREC recommendations.** In Commander, the EDHREC panel of the deckbuilder shows the recommended cards for the selected commander or pair, with their synergy and the share of decks that play them. It also shows the EDHREC average deck. Any recommendation can be added to the deck with Enter.
- **Decks in the Stack account.** Decks are saved automatically and synchronized with the Stack account, encrypted in the same way as inventories, so that only the user can read them. The same decks can be viewed and edited on the Stack website, which has an Arena-style editor designed for phones.
- **Deck share codes.** A deck can be shared with a 10-character code, like inventories. The code opens in Stack (OPEN CODE) or on the Stack website, where the deck can be copied to the recipient's own decks.

### Changed
- The daily cloud download now includes two new files: the rules and legality of every card (about 7 MB) and the META data.
- The English interface includes the texts of the new tabs.
- The StarCityGames and Hareruya price downloads now use 32 connections at a time instead of 16, so they finish in about half the time. Each connection keeps its pause between requests, and the existing protections against rate limits and blocks are unchanged.

### Fixed
- Since version 0.8.0, Stack could stay on the loading screen at 100% and never open. When loading finished, Stack requested the card types and colors (which grew with the cards under $2) and the historical lows and highs at the same time, about 8 MB in single responses, and Windows left the window not responding. These responses, together with the Card Kingdom prices, the format legalities, the card names in other languages and the market summary, are now sent in parts, like the catalog. The heaviest ones are requested one after another after the window opens.
- The loading screen reached 100% before loading had finished, because the step for cards under $2 was not counted. The step now appears in the list, and 100% is shown only when Stack is ready.
- If something fails at the end of loading, Stack now opens anyway, shows a notice and saves the error in data/app/stack_log.txt, instead of staying on the loading screen.

## [0.8.0-beta] - 2026-11-08

This update adds every card printing under US$2 to Stack, with prices from TCG and Card Kingdom every day and from StarCityGames and Hareruya every week. It also adds CSV import from other collection sites and a remove button in the cart.

### Added
- **Cards under $2.** Stack now knows every printing listed on Scryfall, about 118,000 more than before. Some of them have no price yet. The new **< $2** button in the Market filter bar (or the U key on that bar) includes them in searches and lists. It is off by default, so Market looks the same as before until it is turned on. Cards under $2 carry a small "<$2" mark in the list and the gallery. Their TCG and Card Kingdom prices are updated every day, and their StarCityGames and Hareruya prices once a week.
- **Any card in an inventory.** Purchases, imports, share codes and the Stack account now accept cards under $2. Inventories value them at today's price, so the application and the Stack website recognize the same cards.
- **Price history for cards under $2.** To keep the files small, Stack records a new price for these cards only when it moves by at least 10% and at least 5 cents.
- **CSV import.** IMPORT has a new CSV button that opens the collection files exported by Moxfield, ManaBox, Deckbox, Archidekt, TCGplayer, Delver Lens, Dragon Shield and MTGGoldfish. Each row is matched only to its exact printing, using the Scryfall ID when the file has one, or the set, collector number, finish and language. Stack never replaces a row with a similar printing or one with a close price. Rows that do not match are not imported. The summary lists them with the reason (for example, the printing does not exist in foil or the collector number belongs to another card), and COPY THE FULL LIST copies all of them. The rest of the import works like a .stack file: a new or existing inventory, with a count of the cards under $2.
- **Remove from the cart.** Every card in the cart has a ✕ button, in the cart panel, the full cart window, the Market list and the gallery, which removes the card without changing the quantity to zero by hand.
- **Developer tools.** The Hareruya and StarCityGames inconsistency lists have a new **ONLY < $2** chip. It shows the weekly review list for cards under $2: printings that matched with doubts, more than one possible version, or no match.

### Changed
- The daily cloud download includes the files for cards under $2. The first download after updating is larger. After that, only the changes are downloaded, as before.
- The computer that runs the Hareruya prices now also downloads the full Hareruya catalog of cards under $2 once a week. That run takes about 75 minutes longer than a normal day.
- Analysis still uses only cards of $2 or more.

## [0.7.6-beta] - 2026-11-02

This update makes the daily data download about ten times smaller, stops old Hareruya files from piling up on disk and adds filter buttons for color, card type, finish and rarity in Market and Inventory.

### Added
- **Filter buttons in Market and Inventory.** A new row of buttons under the filters selects cards by color (white, blue, black, red, green, colorless and multicolor), card type (land, creature, instant, sorcery, artifact, enchantment, planeswalker and battle), finish (nonfoil, foil and etched) and rarity (common, uncommon, rare and mythic), with the official mana, type and rarity symbols. The buttons can be combined: colors and types require all the selected values (Blue + Red shows blue-red cards), finishes and rarities accept any of the selected values, and the groups apply together (Foil + Blue + Rare shows blue foil rares). Lands count with the colors of the mana they produce, so Blue + Land includes Islands and blue dual lands. The × button clears the selection. In Market the buttons are also reachable with the keyboard from the filter bar (F3, then Down). In Inventory the footer shows how many cards of the inventory match.

### Changed
- **Daily data download.** Stack now records which version of each data file it has. When it opens and the cloud has newer data, it downloads only the rows that changed since the previous day and applies them to the files on the computer, verifying the result. A complete file is downloaded only the first time, after several days without opening Stack or if a file was modified on the computer. A typical day now downloads about 15 MB instead of about 150 MB, most of it the current Hareruya matching file.
- **Smaller price history files.** The price histories of Scryfall, Hareruya, StarCityGames and Card Kingdom are now stored in a compact form that keeps a row only when a price or stock changes. The files read exactly the same prices as before, but take a fraction of the space: with the data available today, the four files take about 130 MB instead of about 480 MB, and they grow much more slowly. The computer that runs the price programs itself keeps the complete Scryfall history.
- Price charts, stock movement and every other view that reads the histories work with both the compact files and the complete files of the main computer.

### Fixed
- Every day a new Hareruya matching file of about 70 MB was saved with a different name and the old ones were never removed. Stack now keeps the two most recent files and deletes the older ones once their prices are in the Hareruya history.

## [0.7.5-beta] - 2026-11-02

This update makes it possible to share an inventory or a bundle with a short code or a QR code, simplifies the export window into three buttons and adds prices to the text export.

### Added
- **Share codes.** An inventory or a bundle can now be shared with a 10-character code (for example K7M4Q-X9P2A) that can be dictated, written down or sent in a message. The cards are encrypted on the computer before they are uploaded, and the code itself is the key, so the Stack server stores only data that it cannot read. Codes expire after 30 days.
- **QR codes.** The same share can be shown as a QR code. Scanning it with a phone opens the inventory on the Stack website with images and today's prices, without installing anything.
- **Open by code.** IMPORT now opens a window where a share code can be typed. Stack downloads and decrypts the cards and shows the same summary as a .stack file before importing them into a new or existing inventory. .stack files can still be opened from the same window.
- **Prices in the text export.** The text file now includes the TCG price in US dollars for each card, and a new section lists each card with its market price per copy and its total, ready to paste into a message. The importable list for Moxfield and Arena is unchanged.

### Changed
- **Export window.** EXPORT now opens a centered window with three buttons, CODE, QR and TXT, and a switch to include or leave out your purchase costs. The code or the QR code appears in the same window, with buttons to copy the code or the link, and the window closes with Esc or the close button.
- **Bundles.** The Share button in the bundle window now creates a code or a QR code for the bundle, including its price, instead of saving a file. Purchase costs are never included in a shared bundle.

## [0.7.4-beta] - 2026-10-31

This update adds Stack inventory files for sharing, records sales with their profit, charts the value of each inventory over time and introduces sale bundles and lot purchases.

### Added
- **Stack inventory files (.stack).** An inventory can be saved as a single .stack file and sent by WhatsApp, e-mail, USB or any other means. The file contains every card with its exact printing, finish and quantity, compressed and marked as a Stack file, so other programs do not open it. The file of a large inventory weighs a few hundred kilobytes.
- **Export menu.** EXPORT in Inventory now offers three formats: a .stack file with your purchase costs (for another of your own computers), a .stack file without costs (to share with customers or partners), and the existing text file for Moxfield and Arena.
- **IMPORT button.** Next to EXPORT, IMPORT opens a .stack file and shows a summary before importing: inventory or bundle name, sender, number of cards and copies, value at today's prices, bundle price and whether costs are included. The cards can be added to a new inventory or to an existing one, and the costs in the file can be used as the acquisition cost. Cards that are not in today's catalog are imported as well.
- **Inventory value chart.** VIEW in Inventory now cycles between Stock on hand, Saved purchases and Value (chart). The chart shows the total market value of the inventory day by day, with the TCG price of each day converted at today's exchange rate, and a dashed line with the amount paid. The current value is shown at the top with the change for the period in pesos and percent. The period can be 7D, 30D, 90D or ALL (Left and Right arrows), and Tab switches between Actual history (the copies held on each day) and What you have today (today's copies at the prices of each day). Hovering over the chart shows the value, the amount paid, the difference and the number of copies for each day.
- **Sales.** SELL in Inventory records the sale of the selected card, or of all marked cards, with the quantity and the price per copy, which starts at today's market price. The window shows the amount received and the profit against the average cost before confirming, and accepts a note. Each sale stores the price, the average cost at that moment and the market price of the day.
- **Purchase and sale history per card.** The card panel in Inventory now lists every entry of the card into the inventory: for purchases, the date, quantity, price paid and market price of that day (hovering shows the margin and the purchase note); for imported or moved copies, their origin. Sales of the card are listed with the price and the profit.
- **Inventory summary.** Next to the chart, Stack shows the market value today, the amount invested in the current stock, the paper profit, the number of sales, the amount received and the realized profit.
- **Sale bundles.** BUNDLE in Inventory groups the marked cards into a bundle with a name, a quantity for each card and a bundle price, which starts at 90% of the value as singles. Stack shows the value as singles, the discount and the profit against cost. The bundle can be sold, which splits the price among the cards according to their market value and records each sale, or saved as a .stack file without costs to send to a customer.
- **Lot purchases.** When saving a purchase, a total price for the whole lot can be entered instead of using the purchase percentage. The total is split among the cards according to their market value, so each card keeps a real acquisition cost. Stack shows the equivalent percentage of the market, the ROI, the gross margin and the potential margin before saving, and the lot price is added to the purchase note.

### Changed
- Sales, imports from .stack files and lot purchases are synchronized with the Stack account like any other inventory change. The sale records themselves are stored only on the computer.

## [0.7.3-beta] - 2026-10-27

This update turns the movers on the home page into a rotating exhibit that also includes the watchlist, gives the home page more room and shows the animated background of the theme behind it.

### Changed
- **Rotating exhibit on the home page.** The row of movers now scrolls by itself as a continuous strip, without a scroll bar, and pauses while the pointer is over it. After the day's movers it shows the watchlist cards that have a price alert, with the target price, and then the rest of the watchlist with its price change. Each card shows its image, printing and current price, and a click opens the card details. Tab still switches between cards that went up and cards that went down. When animations are turned off, the cards are shown without movement.
- **Layout of the home page.** The content is centered, with more space between sections and between the lines of each card.
- **Animated background.** With animated themes (Plasma, Grid Shift, Contour and Galaxy) and with a custom background image, the background is now visible behind the home page instead of a solid color.
- **Esc on the home page.** Esc no longer leaves the home page and returns to the previous view; it now does nothing there. The home page is left with any tab (F5 to F8). Inside an article, Esc still returns to the home page.
- **Keyboard on the home page.** The arrow keys move between articles and Enter opens the selected one. Clicking the logo while reading an article returns to the home page.

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
