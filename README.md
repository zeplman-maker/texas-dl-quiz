# texas-dl-quiz
A Progressive Web App (PWA) that installs on any Android device as a full-screen app — no app store, no APK required. Works offline after first load. 75 questions
=====================================================
  TEXAS DL QUIZ — PWA (Android / iOS / Desktop)
=====================================================

WHAT IS THIS?
A Progressive Web App (PWA) that installs on any Android device
as a full-screen app — no app store, no APK required.
Works offline after first load. 75 questions.

=====================================================
  HOW TO INSTALL ON ANDROID (3 options)
=====================================================

──────────────────────────────────────────────────
OPTION A: GitHub Pages (FREE — recommended)
──────────────────────────────────────────────────
1. Go to github.com and create a free account (if needed)
2. Create a new repository — call it: texas-dl-quiz
   Set it to PUBLIC
3. Upload all files in this folder:
     index.html
     manifest.json
     sw.js
     icons/icon-192.png
     icons/icon-512.png
4. Go to Settings → Pages → Source: "main" branch / root
5. Click Save — GitHub gives you a URL like:
     https://yourusername.github.io/texas-dl-quiz/
6. Open that URL in Chrome on your Android phone
7. Chrome shows a banner: "Add Texas DL Quiz to Home Screen"
   — tap Install or use Chrome menu (⋮) → "Add to Home Screen"
8. Done — the app icon appears on your home screen

──────────────────────────────────────────────────
OPTION B: Netlify Drop (FREE — fastest, no account)
──────────────────────────────────────────────────
1. Go to: https://app.netlify.com/drop
2. Drag the entire "texas_dl_pwa" FOLDER onto the page
3. Netlify gives you a live URL instantly (e.g., random-name.netlify.app)
4. Open that URL in Chrome on your Android phone
5. Tap the install banner → installed as a home screen app

──────────────────────────────────────────────────
OPTION C: Local network (no internet required)
──────────────────────────────────────────────────
1. On your PC, open a terminal in this folder and run:
     python -m http.server 8080
   (Python 3 required — it's likely already installed)
2. Find your PC's local IP address (e.g., 192.168.1.5)
   Windows: run "ipconfig" → look for IPv4 Address
3. On your Android phone (same WiFi network), open Chrome
4. Go to: http://192.168.1.5:8080
5. Tap Chrome menu (⋮) → "Add to Home Screen"

NOTE: Option C uses HTTP (not HTTPS). The service worker
won't register on HTTP for security reasons, so offline
support is disabled in this mode. The quiz still works
fully — just not offline.

=====================================================
  HOW TO INSTALL ON iOS (iPhone/iPad)
=====================================================
1. Host the files using Option A or B above
2. Open the URL in Safari (NOT Chrome — must be Safari)
3. Tap the Share button (square with arrow)
4. Scroll down → "Add to Home Screen"
5. Tap Add

=====================================================
  FILE STRUCTURE
=====================================================
texas_dl_pwa/
├── index.html          ← Main quiz app (75 questions)
├── manifest.json       ← PWA config (name, icons, colors)
├── sw.js               ← Service worker (offline cache)
├── icons/
│   ├── icon-192.png    ← Home screen icon (Android)
│   └── icon-512.png    ← Splash / high-res icon
└── README.txt          ← This file

=====================================================
  WANT A REAL APK INSTEAD?
=====================================================
Use Capacitor to wrap this as a native .apk:

1. Install Node.js from nodejs.org
2. Run these commands in this folder:
     npm init -y
     npm install @capacitor/core @capacitor/cli @capacitor/android
     npx cap init "Texas DL Quiz" "com.txdl.quiz"
     npx cap add android
     # Copy your web files into the www/ folder first
     npx cap sync android
     npx cap open android
3. Android Studio opens → Build → Generate Signed APK
4. Upload to Google Play or share the APK directly

The PWA approach above is recommended for personal use.
Capacitor is needed for Google Play Store distribution.

=====================================================
  QUIZ CONTENT
=====================================================
75 questions in two sets:
- Set 1 (Q1–25):  Most commonly missed questions
                  (iDriveSafely, DriversEd.com, driving-tests.org data)
- Set 2 (Q26–75): Harder Texas-specific questions
                  (Move Over Law, teen restrictions, DWI details,
                   parking distances, railroad crossings, etc.)

Source: Texas Driver Handbook DL-7 (January 2026 edition)
        Texas DPS — dps.texas.gov

=====================================================
