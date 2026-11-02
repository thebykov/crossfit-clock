# Class Hour Clock

A phone app for planning and running a 60-minute CrossFit class: brief, class warm-up, Part A warm-up, Part A (with optional every-X-minute rounds), a transition that flexes to keep Part B on its planned minute, and Part B.

It's a static web app (PWA). No server, no build step, no accounts. Settings stay on each phone.

## Deploy with GitHub Pages
1. Push these files to a public repo.
2. In the repo go to Settings > Pages, set Source to "Deploy from a branch", branch `main`, folder `/ (root)`, and save.
3. The app will be live at `https://<your-username>.github.io/<repo-name>/` in a minute or two.

## Deploy on your own website instead
Upload every file and folder here into one folder on your site, for example `yoursite.com/class-clock/`. It must be served over HTTPS.

## Install on a phone
- iPhone: open the link in Safari, tap Share, then Add to Home Screen. Open it from the home screen icon, then turn on Notifications in the Alerts section.
- Android: open the link in Chrome, then tap Install app (or menu > Add to Home screen).

## Updating
After changing any file, bump `VERSION` in `sw.js` (for example `chc-v2`) so phones pick up the new version. Phones update the next time the app is opened while online.

## How background alerts work
When a class starts, the app renders every upcoming beep into one audio track and plays it. Audio keeps playing with the screen locked or the app in the background, so the beeps land on time even when JavaScript is paused. The track is rebuilt whenever you tap Next, Pause or Resume.
Notifications fire when the phone lets the app run in the background. That's reliable on Android; on iPhone they are best-effort, and the beeps are the dependable alert.
