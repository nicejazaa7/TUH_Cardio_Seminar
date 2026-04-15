# Seminar Tracker — Setup Guide

## What you need
- A free Google account (for Firebase)
- A free GitHub account (for hosting)
- The `index.html` file from this folder

---

## Step 1 — Create a Firebase project (5 minutes)

1. Go to https://console.firebase.google.com
2. Click **"Add project"** → name it `seminar-tracker` → click through (disable Analytics is fine)
3. Once created, click the **web icon `</>`** to add a web app
4. Name it anything (e.g. `seminar-web`) → click **Register app**
5. You'll see a block of code like this — **copy these values**:

```js
const firebaseConfig = {
  apiKey: "AIzaSyCkLioeUv8FWGPFcc35SfFsrx1yvtCvAQg",
  authDomain: "seminar-quota-tracker.firebaseapp.com",
  projectId: "seminar-quota-tracker",
  storageBucket: "seminar-quota-tracker.firebasestorage.app",
  messagingSenderId: "130438789226",
  appId: "1:130438789226:web:769f00aec1b3d1a2bdb213",
  measurementId: "G-8S65WTBYL7"
};
```

6. In the Firebase Console left sidebar → **Build → Realtime Database**
7. Click **Create Database** → choose your region → start in **Test mode** (you can secure it later)

---

## Step 2 — Paste your Firebase config into index.html

1. Open `index.html` in any text editor (Notepad, TextEdit, VS Code)
2. Find this section near the top of the `<script>`:

```js
const FIREBASE_CONFIG = {
  apiKey:            "REPLACE_WITH_YOUR_API_KEY",
  authDomain:        "REPLACE_WITH_YOUR_AUTH_DOMAIN",
  ...
```

3. Replace each `"REPLACE_WITH_..."` value with the real values from Step 1
4. Also change the PIN if you want (find `const CHIEF_PIN = '1234'`)
5. Save the file

---

## Step 3 — Host on GitHub Pages (free)

1. Go to https://github.com and create a free account if you don't have one
2. Click **"New repository"** → name it `seminar-tracker` → set to **Public** → click **Create**
3. On the next page, click **"uploading an existing file"**
4. Drag and drop your `index.html` file → click **Commit changes**
5. Go to **Settings → Pages** (left sidebar)
6. Under **Source**, select `main` branch → click **Save**
7. Wait 1–2 minutes → your site will be live at:
   `https://YOUR-GITHUB-USERNAME.github.io/seminar-tracker`

---

## Sharing with your team

- Share the GitHub Pages URL with your fellows — they open it on phone or desktop
- They always land on **Team view** (read-only) by default
- Only you know the PIN to switch to **Chief view** and edit data
- All data is stored in Firebase — changes appear instantly on all devices

---

## Data safety

- Firebase Realtime Database keeps your data permanently in Google's cloud
- Data is NOT lost when you close the browser or share the link
- If Firebase is not set up, the app falls back to browser localStorage (data stays on that device only)
- To back up your data: Firebase Console → Realtime Database → the three-dot menu → Export JSON

---

## Changing the PIN

Open `index.html`, find this line and change `'1234'` to anything you want:

```js
const CHIEF_PIN = '1234';
```

---

## Updating the fellows list

Open `index.html`, find this line to add or rename fellows:

```js
const FELLOWS = ['Nice','Nut','Mane','Kaowpoon','Artie','Pong','Brat','KK'];
```
