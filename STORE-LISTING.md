# Chrome Web Store listing (copy and paste into the developer dashboard)

Everything the store asks for, in the order the dashboard asks. Fill in the two
**TO DO** items before submitting.

## Store listing tab

**Name** (comes from the extension itself, 45 characters, the store limit)

    Plot Armor: Spoiler Blocker for Movies & TV

**Summary** (also comes from the extension; 119 of 132 characters)

    Covers spoilers on X for the shows, movies and wrestling you haven't seen yet. Mark it watched and the covers lift.

**Description**

    Watch it your way. Plot Armor covers spoilers on X (Twitter) for the shows and live events you haven't seen yet.

    Add a show, tell Plot Armor the last episode you've watched, and any post about something newer gets a "Possible spoiler" cover. Watched it? Tick the episode and the covers lift on their own. Starting a show from the beginning? Choose "Hide everything" and nothing about it gets through.

    WHAT IT COVERS
    • WWE: RAW, SmackDown, NXT and premium live events, each tracked separately
    • AEW: Dynamite, Collision and pay-per-views
    • Survivor, The Amazing Race, Big Brother, The Traitors, and more on the way
    • Movies too: hide trailers, set photos and leaks for a big release (starting with Avengers: Doomsday) until you've seen it
    • Posts, quote posts, replies under a covered post, link previews and photo descriptions
    • The "What's happening" trends sidebar, which is covered completely on the night an episode airs

    BUILT FOR LIVE TV
    • Episode nights: names and hashtags that suddenly trend about your show are picked up automatically while you browse
    • "Watching live tonight": see everything for the night, switches itself off at 4 AM
    • Protect a big event (a pay-per-view, a finale) with one tap, before it starts
    • "Did you watch it?": a gentle reminder after an episode airs, so covers never pile up

    YOUR CHOICE, EVERY TIME
    • "Show anyway" uncovers a single post
    • "I've watched this" right on the cover marks the episode watched
    • A thin bar or a full blur: pick how covered posts look

    PRIVATE BY DESIGN
    Everything happens on your computer. No account, no sign-in, no tracking, no ads. Plot Armor never sends what you read anywhere. Its only connection to the internet is a daily download of the show lists (episode dates and cast names).

    Plot Armor is not affiliated with X or with any show, network or wrestling company it covers. Show names are used only to say which shows it supports.

**Category**: Social & Communication (if the dashboard's list differs, the closest "social" or
"entertainment" category).

**Language**: English (United States).

**Graphic assets**
- Store icon: `public/icon/128.png` (already in the extension too).
- Screenshots: at least one, 1280×800. Take them on your Mac, then run
  `npm run store-screenshot -- <file>` to fit each one to 1280×800 (see below).
  Good ones: (1) an X timeline with two or three covered posts; (2) the popup on My shows;
  (3) the WWE hub; (4) a covered "What's happening" box on an episode night.
- Small promo tile (optional, 440×280): `store/promo-tile-440x280.png`.

## Privacy tab

**Single purpose**

    Plot Armor hides posts on X about TV shows and live events until the user has watched them.

**Permission justifications**
- `storage`: Saves the user's tracked shows, last-watched episodes, settings and a copy of the show lists in the browser, on the user's computer.
- `alarms`: Runs a once-a-day timer to download updated show lists (episode dates and cast names), and an hourly check that updates the "Did you watch it?" count on the toolbar icon.
- Host access (`x.com`, `twitter.com`, through the content script): Reads the posts and trending topics on X pages, on the user's computer, to decide which ones to cover with a spoiler warning. It runs on no other site.

**Remote code**: No, I am not using remote code. (The downloaded show lists are plain JSON data
files, checked before use; no code is downloaded.)

**Data usage**: Plot Armor reads page content on X only to decide what to cover, entirely on the
device, and never transmits it. If the form treats on-device reading as "collecting", tick
**Website content** and nothing else. Then tick all three statements: not sold to third parties;
not used for purposes unrelated to the single purpose; not used for creditworthiness or lending.

**Privacy policy URL**: `https://sellybros711.github.io/spoiler-blocker-data/privacy.html`
(upload `store/privacy.html` to the spoiler-blocker-data repo first).

## Distribution tab

- **Visibility: Unlisted** (only people with the link can find it). Switch to Public once
  Phase 1 has proven itself.
- **Regions**: all, or United States only for the beta.
- Payments: **Free of charge**. WHEN PRO LAUNCHES: switch this to **Contains in-app purchases**
  (the store then shows an "in-app purchases" badge), update the description, and update
  `store/privacy.html` for whatever the payment flow collects. Do this before the paid version
  is submitted.

## TO DO before submitting
1. Upload `store/privacy.html` to the data repo (contact: RunTheGames@outlook.com).
2. Take the screenshots.
3. `npm run zip` and upload `.output/plot-armor-<version>-chrome.zip`.

## Fitting a screenshot to 1280×800

    npm run store-screenshot -- ~/Desktop/my-screenshot.png

It scales the picture to fit and fills the rest with the Plot Armor violet, and saves
`my-screenshot-1280x800.jpg` next to it (a JPEG: the store refuses PNGs with transparency).
Uses `sips`, which comes with macOS. A finished one is in `store/screenshots/`.
