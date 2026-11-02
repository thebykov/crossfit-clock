# CrossFit Clock

**Live app:** https://thebykov.github.io/crossfit-clock/

A phone app for planning and running a 60-minute CrossFit class. Set how long each part takes, hit Start, and coach to one big clock that keeps the class on the hour.

## How a class is laid out

| Phase | How it runs |
|---|---|
| Brief | Counts down, then waits for you to tap **Next** |
| Class warm-up | Counts down, then waits for you to tap **Next** |
| A warm-up | Bar setup and warm-up sets. Runs on the clock |
| Part A | Runs on the clock. Optional rounds every 1:00 to 5:00 (for example every 3:00 for 24 minutes = 8 rounds) |
| Transition | Recover, put weights away, set up and warm up for Part B. **Flexes** so Part B starts on its planned minute |
| Part B | Runs on the clock. Optional rounds, same as Part A |
| Wrap-up | Whatever is left of the hour |

- Part A and Part B always get their full time.
- If the brief or class warm-up runs long, the transition gets shorter (never below 1:00). If they run short, it gets longer.
- Turn Part B off for a single longer workout.
- The pace banner tells you if you're on time, what the transition became, or how far past the hour you'll run.

## Install on a phone

- **iPhone:** open the link in Safari, tap Share, then **Add to Home Screen**. Open it from the home screen icon.
- **Android:** open the link in Chrome, then tap **Install app** (or menu → Add to Home screen).

Settings are saved on each phone, and the app works offline once installed.

## Alerts

- **Beeps:** 3-2-1 before every phase and round change, then a long start beep. Before class, use **Test beep** to check volume. The beeps play as media audio, so turn up media volume.
- **Notifications:** a banner when a new phase starts while the app is in the background. On iPhone, add the app to the Home Screen first, then turn this on in the Alerts section.
- **Lock screen:** shows the current phase and round, with a pause button.

### How background beeps work
When a class starts, the app renders every upcoming beep into one audio track and plays it. Phones keep audio playing with the screen locked or the app in the background, so the beeps land on time even when the app itself is paused. The track is rebuilt whenever you tap Next, Pause or Resume.

Notifications only fire when the phone lets the app run in the background. That's reliable on Android. On iPhone, treat the beeps as the alert you can count on.

## Hosting and updates

Hosted on GitHub Pages from the `main` branch, root folder (Settings → Pages). Pushing to `main` redeploys in a minute or two.

**After changing any file, bump `VERSION` in `sw.js`** (for example `chc-v1` → `chc-v2`). Phones pick up the new version the next time the app opens while online.

## Files

- `index.html` is the whole app (layout, styles and logic)
- `sw.js` is the service worker for offline use, updates and notification taps
- `manifest.webmanifest` holds the app name, icons and colors used when installing
- `icons/` holds the app icons
- `fonts/` holds the bundled fonts (Big Shoulders Display, Archivo), so the app needs no internet for fonts

No server, no build step, no accounts.
