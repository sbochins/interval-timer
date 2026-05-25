# Interval Timer

A clean, single-file interval timer for workouts. Build a workout out of segments
and repeating cycles (warmup / work / rest / cooldown), then run it with big,
glanceable countdowns, audio cues, and vibration.

**Live:** https://intervaltimer.bochinski.dev

## Use it as an app (iPhone / Safari)

1. Open the site in Safari.
2. Tap the **Share** button → **Add to Home Screen**.
3. Launch it from the home-screen icon — it opens fullscreen, with no Safari chrome.

Once opened online at least once, it works **offline** (service worker caches the app).

### What works on iOS

- **Screen stays awake** during a running workout (Screen Wake Lock, iOS 16.4+), so it
  won't dim while you're watching the countdown.
- **Accurate after lock/app-switch.** Time is tracked from the wall clock, so if the
  screen locks or you switch apps, the timer snaps to the correct phase when you return
  rather than drifting.

### iOS limitation (by design of the web platform)

iOS suspends web pages in the background. A web app **cannot** keep counting or play
audio cues while you're in another app or the screen is locked — that needs a native
app. Keep the timer in the foreground during a workout; Wake Lock keeps the screen on
so you don't have to.

## Develop / preview locally

It's a static site — just serve the folder:

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Hosting

Static site on GitHub Pages, served from the repository root on `main`, with the custom
domain in `CNAME` (`intervaltimer.bochinski.dev`).
