<div align="center">

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:667eea,50:764ba2,100:f093fb&height=300&section=header&text=%20Web%20Studio%20Pro&fontSize=60&fontColor=ffffff&animation=fadeIn&fontAlignY=40&desc=Your%20Browser%20Is%20Now%20A%20Production%20Studio&descAlignY=65&descSize=20" alt="Web Studio Pro Header"/>

<br>

![Version](https://img.shields.io/badge/Version-1.0-blue.svg?style=for-the-badge)
![Tech Stack](https://img.shields.io/badge/Tech-Vanilla_JS_|_CSS3_|_HTML5-f0db4f.svg?style=for-the-badge&logo=javascript)
![API](https://img.shields.io/badge/API-MediaDevices_Web_RTC-ff69b4.svg?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)

</div>

> **A professional, zero-installation staging and recording studio built entirely in the browser.**

Turn your web browser into a high-fidelity presentation powerhouse. Getting pristine, professional-looking screen recordings of web apps usually requires expensive software, green screens, or tedious video editing. Not anymore. 

Web Studio Pro wraps your live web projects in exquisite, CSS-rendered device mockups and utilizes native browser APIs to let you record high-framerate videos, narrate with your microphone, and overlay a presenter facecam—all instantly, and all for free.

---

## Live Demo
**[Click here to launch the Studio](https://leemeeooo.github.io/webstudio)** *(Requires a modern desktop browser for full recording capabilities).*

---

## Core Features

* **Exquisite Device Mockups:** Frame your app perfectly inside a Pro Laptop, Studio Monitor, iPhone, Android, Smartwatch, Television, or edge-to-edge Full Screen.
* **Presenter Facecam:** Inject a beautifully styled, floating circular webcam bubble into the corner of your stage to record software tutorials and pitches.
* **Voice Narration:** Mix your microphone audio directly into your screen recordings in real-time.
* **Infinite Customization:** Change device chassis colors and background styles with a click. Choose between clean solid colors or a dynamic, animated aurora gradient.
* **Lossless Native Capture:** Snap clean `.png` pictures or record crisp 60fps `.webm` videos directly to your hard drive using the browser's native `MediaDevices` API.
* **Custom Branding:** Upload your own transparent `.png` logo to automatically watermark your stage.
* **Dynamic Orientation:** Instantly rotate mobile devices to showcase widescreen layouts and mobile games.

---

## How to Use It

### 1. Staging Your App
1. Paste the URL of your live web app into the top input bar.
2. Click **Load**.
3. Use the **Device** dropdown to select your preferred hardware frame. 
4. *Pro Tip:* Use the **Rotate** button to switch mobile mockups between portrait and landscape.

### 2. Capturing Media
* **Picture:** Click `Picture`. The UI dock will instantly hide, the stage will be captured, and a `Studio_Capture.png` will download to your device.
* **Video:** Click `Record`. Select the specific Chrome Tab you are currently viewing. The controls will vanish, leaving a pristine stage. Interact with your app normally. When finished, press `Escape` and click `Stop`. A `Studio_Video.webm` file will download instantly.
* **Presenting:** Toggle `Cam: ON` and `Mic: ON` before hitting record to create a complete tutorial video.

---

## The "Secret Tricks" Playbook

### The Google Drive Video Trick
You can use this studio to beautifully frame videos hosted on Google Drive, but the standard sharing link won't work due to Google's embedding rules. You must modify the URL:
1. Get your Drive sharing link: `https://drive.google.com/file/d/123xyz.../view`
2. Change `/view` to `/preview`.
3. Your new link is: `https://drive.google.com/file/d/123xyz.../preview`
4. Paste this into the Studio! 

*(Note: When recording a video with sound, ensure you check "Also share tab audio" when the browser prompts you to select a screen).*

---

## Known Limitations (The Iframe Wall)

### Clickjacking Protection (`X-Frame-Options`)
You cannot paste *any* website into this studio. If you try to load major sites like Twitter, GitHub, or Shopify, the screen will remain blank. 

**Why?** Modern websites use a security header called `X-Frame-Options` or Content Security Policies (CSP) to actively block other websites from putting them inside an `<iframe>`. This is a global internet security standard to prevent hackers from tricking users. 

**The Fix:** This studio is designed specifically for **your** apps. As long as you control the code of the project you are pasting, you can display it:
* **For Google Apps Script:** Add `.setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)` to your `doGet()` function.
* **For Node.js/React/Vercel:** Remove `X-Frame-Options` restrictions in your deployment headers for your recording sessions.

### Browser Permissions
The studio requires explicit, top-level permission to view your screen, use your microphone, and access your camera. If the capture buttons fail, check your browser's address bar for a "blocked camera/screen" icon and reset your site permissions, or check your OS Privacy settings.

---

## Tech Stack
Built entirely with vanilla web technologies for maximum speed and zero dependencies:
* **HTML5 & CSS3** (Advanced CSS shapes, gradients, and variables for device mockups).
* **Vanilla JavaScript** (ES6+).
* **MediaDevices API** (`getDisplayMedia`, `getUserMedia`, `MediaRecorder` for native A/V capture).
* **HTML Canvas API** (For lossless PNG frame extraction).

---

*Designed and Built for Web Developers & Content Creators.*
