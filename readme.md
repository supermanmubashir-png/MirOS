# MirOS Browser Edition

MirOS is a browser-based personal workspace built with vanilla HTML, CSS and JavaScript. It provides a desktop-style interface, local apps, MirStore, a virtual file area, personalization and offline shell caching. It does not replace Windows or run native desktop applications.

## Project files

The project contains exactly nine source/documentation files:

1. `index.html` — startup and boot screen.
2. `setup.html` — first-time setup wizard.
3. `home.html` — desktop, taskbar, Start Menu, panels and lock screen.
4. `style.css` — interface styling, animations and responsive layouts.
5. `app.js` — app catalogue, window manager, settings, storage and interactions.
6. `manifest.json` — PWA metadata.
7. `sw.js` — service worker and offline shell cache.
8. `help.html` — end-user Help Center.
9. `readme.md` — this documentation.

## User-supplied assets

Keep these assets beside the nine files. They are referenced by the project but are not included in the source ZIP:

- `icon.png` — MirOS icon used by the page and PWA manifest.
- `wallpaper.png` — default wallpaper (Wallpaper 1).
- `wallpaper2.png` — alternate wallpaper (Wallpaper 2).

File names are case-sensitive on many hosting services. Upload all assets to the same project directory as `home.html`.

## Install and run

1. Upload the nine project files and three user-supplied assets to the same HTTPS site directory.
2. Open `index.html` in a modern browser.
3. Complete the first-time setup wizard.
4. After setup, MirOS returns to the boot screen and then the lock screen.
5. Install optional website apps from MirStore. MirCodeStudio is included by default.

For PWA installation and service-worker/offline support, serve MirOS from HTTPS (for example, GitHub Pages). Direct `file://` opening does not provide service-worker support and may restrict browser APIs.

## Features

- 20-second boot sequence with a repeating left-to-right moving segment (no percentage counter).
- Expanded setup wizard with wallpaper image choices, profile, region, display, accessibility, sound, network, local backup, app selection, mobile layout and motion preferences.
- Two-stage lock screen with clock/wallpaper followed by the selected unlock interface.
- Desktop shortcuts, grid placement, taskbar pins, Start Menu and app windows.
- MirStore with optional website app installation.
- Wallpaper Studio with `wallpaper.png`, `wallpaper2.png`, built-in backgrounds and custom image support.
- Local profile and browser-managed virtual files.
- Sound effects, settings, notifications and offline shell caching.
- Responsive layout for desktop, tablets and phones.
- Help Center at `help.html`.

## Storage and privacy

MirOS stores settings and app state in browser storage and virtual files in IndexedDB where available. Clearing site data, using a private browsing session, or changing browser profiles may remove local MirOS data. Export backups before clearing browser storage.

External website apps run under their own sites and privacy policies. MirOS does not control their cookies, accounts, or server-side data. The project does not require Google sign-in. Do not add private API keys, OAuth secrets, tokens, passwords or developer credentials to public source files.

## Offline behavior

The service worker caches the MirOS shell and attempts to cache the optional wallpaper and icon assets when present. Missing user-supplied images do not prevent installation. Local app functionality may continue offline; external websites and live online services still require internet. Offline support depends on what each app and external website provides.

## Browser limitations

- MirOS runs inside a browser and cannot power off Windows or force Edge to close its window.
- Shutdown ends the MirOS session and presents a powered-off state; the browser may keep the tab open.
- Browser security policies may block external websites from being embedded. Use the open-in-browser fallback.
- Browser permissions govern local file access, camera, microphone, location and notifications.
- A fingerprint-style tap-to-unlock option is a convenience gesture, not proof of biometric identity.
- Service workers require a secure context such as HTTPS or localhost.

## Troubleshooting

- If the interface looks outdated after deployment, refresh and reopen the site so the new service worker can activate.
- If wallpapers are missing, confirm that both PNG files are uploaded beside the HTML files with exact names.
- If offline support does not activate, confirm the site uses HTTPS and that `sw.js` is reachable.
- If local storage is full or disabled, remove unneeded MirOS data only after exporting anything important.

## Help

Open `help.html` from the taskbar, Start Menu, Settings, MirStore or directly from the site.
