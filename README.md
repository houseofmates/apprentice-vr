# apprentice vr — pkm edition

> a personalized fork with a beautiful dark theme, collapsible ui sections, and enhanced user experience

<div align="center">
  <img src="./build/icon.png" alt="apprentice vr logo" width="120">

  **download, manage, and install quest vr games with style**
</div>

---

## what makes this fork different?

this is a personalized fork featuring the **pkm aesthetic** — a warm, modern dark theme designed for comfortable extended use. the original [apprentice vr](https://github.com/houseofmates/apprentice-vr) is excellent, but i wanted something that felt more personal and matched my workflow preferences.

### 🎨 visual design changes
- **solid dark backgrounds** — `#050505` base with no gradients or glows
- **varela round typography** — clean, lowercase ui text throughout
- **warm color palette** — yellow (`#f6b012`) primary accents with blue (`#3c9fdd`) info colors
- **consistent button styling** — subtle hover effects with border highlights
- **smooth micro-animations** — 200ms cubic-bezier transitions everywhere

### ✨ ux improvements
- **collapsible sections** — settings organized into expandable panels for cleaner ui
- **unified navigation** — games and settings accessible from header buttons
- **slide-out drawers** — downloads and uploads in overlay panels instead of separate pages
- **better visual hierarchy** — clear distinction between primary and secondary actions
- **responsive layouts** — better handling of various window sizes

### 🧩 new components
- **`CollapsibleSection`** — reusable accordion component for organizing complex forms
- **custom fluent theme** — complete dark theme override (`pkmTheme.ts`)
- **enhanced device cards** — cleaner layout with wifi bookmark indicators and status badges

---

## features

### game management
- browse and search game library with real-time filtering
- view installed vs available games at a glance (color-coded: green = installed, yellow = update available)
- automatic version checking with update notifications
- bulk download queue management

### device connectivity
- usb and wifi/tcp connection support
- wifi device bookmarking for quick reconnection
- real-time device status with ping monitoring
- battery and storage info display
- automatic quest device detection

### downloads & uploads
- parallel download management with progress tracking
- configurable speed limits (kb/s or mb/s)
- automatic extraction and installation
- upload queue for sharing content

### settings (now with collapsible sections!)
- **download settings** — customizable download location with folder picker
- **speed limits** — bandwidth throttling controls for download/upload
- **log upload** — share logs for support/debugging via catbox.moe
- **blacklist management** — manage games excluded from upload prompts

---

## screenshots

**device list**
![device list](screenshots/01_devices_dark.png)

**game library**
![game library](screenshots/02_library_light.png)

**game details**
![game details](screenshots/03_detail_light.png)

**downloads manager**
![downloads manager](screenshots/04_download_dark.png)

---

## installation

### requirements
- windows 10/11, macos, or linux
- meta quest headset (quest 1, 2, 3, or pro)
- usb cable or wifi connectivity (quest must have developer mode enabled)

### quick start

1. **download** the latest release for your platform
2. **connect** your quest via usb (enable developer mode first)
3. **browse** games and click to download/install

### building from source

```bash
# clone the repository
git clone https://github.com/yourusername/apprentice-vr.git
cd apprentice-vr

# install dependencies (pnpm recommended)
pnpm install

# run in development mode
pnpm dev

# build for your platform
pnpm build:win   # windows
pnpm build:mac   # macos
pnpm build:linux # linux
```

---

## macos specifics

since the application is not signed by an apple developer id, when you first try to open apprenticevr.app on macos, you might see: "apprenticevr is damaged and can't be opened."

to resolve this, run in terminal:

```bash
xattr -c /Applications/apprenticevr.app
```

adjust the path if you placed the app elsewhere.

---

## logs

by default, logs are written to:

- **linux:** `~/.config/apprenticevr/logs/main.log`
- **macos:** `~/library/logs/apprenticevr/main.log`
- **windows:** `%userprofile%\appdata\roaming\apprenticevr\logs\main.log`

you can also upload the current log file directly from the settings menu and share the url for support.

---

## troubleshooting

### device not detected
1. enable developer mode on your quest
2. allow usb debugging when prompted on headset
3. try a different usb port/cable
4. restart the adb server: `adb kill-server && adb start-server`

### wifi connection issues
1. ensure quest and pc are on the same network
2. check that port 5555 is not blocked by firewall
3. try connecting via usb first, then switch to wifi

### connection problems
1. **check network access** — ensure you can reach these urls:
   - https://raw.githubusercontent.com/
   - https://downloads.rclone.org/
   - https://go.vrpyourself.online/

2. **change dns** — some isps block domains. try:
   - [cloudflare (1.1.1.1)](https://developers.cloudflare.com/1.1.1.1/setup/)
   - [google (8.8.8.8)](https://developers.google.com/speed/public-dns/)

3. **use a vpn** — if dns doesn't help:
   - [protonvpn (free)](https://protonvpn.com/)
   - [1.1.1.1 vpn (free)](https://one.one.one.one/)

4. **router/firewall** — whitelist these domains if needed:
   - raw.githubusercontent.com
   - downloads.rclone.org
   - go.vrpyourself.online

---

## development

### prerequisites
- [node.js](https://nodejs.org/)
- [pnpm](https://pnpm.io/installation) (recommended)

### commands

```bash
pnpm install    # install dependencies
pnpm dev        # run in development mode
pnpm lint       # lint codebase
pnpm format     # format with prettier
```

### recommended ide
- [vscode](https://code.visualstudio.com/) with eslint and prettier extensions

---

## technology

built with:
- **electron** — cross-platform desktop framework
- **react 18** — ui library
- **fluent ui** — microsoft's design system (heavily customized)
- **tanstack table** — performant data tables
- **adb** — android debug bridge for device communication
- **rclone** — cloud storage downloads

---

## credits

- original [apprentice vr](https://github.com/houseofmates/apprentice-vr) project by house of mates
- inspired by [rookie sideloader](https://github.com/VRPirates/rookie)
- theme design based on pkm (personal knowledge management) aesthetic principles
- icons from fluent ui icons

---

## license

this project is provided as-is for personal use. please respect the original project's licensing terms.

---

<div align="center">
  <sub>made with care for the quest community</sub>
</div>
