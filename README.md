# DocScan - Android App

A document scanning app built with Kotlin, CameraX, ML Kit OCR, and Room database.

---

## 🚀 How to Build the APK via GitHub Actions

### Step 1 — Create a GitHub Repository
1. Go to [github.com](https://github.com) and sign in (or create a free account)
2. Click **"New repository"**
3. Name it `DocScan`, set it to **Public** or **Private**
4. Click **"Create repository"**

### Step 2 — Upload the Project
**Option A — GitHub Website (easiest):**
1. On your new repo page, click **"uploading an existing file"**
2. Drag and drop the entire `DocScan` folder contents
3. Click **"Commit changes"**

**Option B — Git command line:**
```bash
cd DocScan
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/DocScan.git
git push -u origin main
```

### Step 3 — Trigger the Build
- The workflow runs **automatically** on every push to `main`
- To trigger manually: go to **Actions → Build DocScan APK → Run workflow**

### Step 4 — Download the APK
1. Go to the **Actions** tab in your GitHub repo
2. Click the latest **"Build DocScan APK"** run
3. Scroll to **Artifacts** at the bottom
4. Click **"DocScan-debug-apk"** to download
5. Unzip the downloaded file — your `app-debug.apk` is inside!

### Step 5 — Install on Android
1. Transfer the APK to your Android device
2. Enable **"Install from unknown sources"** in Settings → Security
3. Tap the APK file to install

---

## 🏗️ Project Structure

```
DocScan/
├── .github/
│   └── workflows/
│       └── build-apk.yml       ← GitHub Actions workflow
├── app/
│   └── src/main/
│       ├── java/com/nanotech/docscan/
│       │   ├── MainActivity.kt
│       │   ├── data/
│       │   │   ├── model/       Document.kt, DocumentPage.kt, Folder.kt
│       │   │   ├── local/       DocumentDao.kt (Room)
│       │   │   └── repository/  DocumentRepository.kt
│       │   └── ui/
│       │       ├── home/        HomeFragment.kt
│       │       ├── scan/        ScanFragment.kt (CameraX)
│       │       ├── edit/        EditFragment.kt
│       │       ├── ocr/         OCRFragment.kt (ML Kit)
│       │       ├── settings/    SettingsFragment.kt
│       │       ├── premium/     PremiumFragment.kt
│       │       └── viewmodel/   DocumentViewModel.kt
│       ├── res/
│       │   ├── layout/          XML layouts for all screens
│       │   └── navigation/      nav_graph.xml
│       └── AndroidManifest.xml
└── build.gradle
```

---

## 🔑 App Details

| Property       | Value                    |
|----------------|--------------------------|
| Package        | `com.nanotech.docscan`  |
| Min Android    | 7.0 (API 24)             |
| Target Android | 14 (API 34)              |
| Language       | Kotlin                   |
| Architecture   | MVVM + Repository        |

## 📦 Key Dependencies

| Library              | Purpose                        |
|----------------------|--------------------------------|
| CameraX              | Camera preview & capture       |
| ML Kit Text Rec.     | OCR / text extraction          |
| Room                 | Local database                 |
| iText PDF            | PDF generation                 |
| AdMob                | Advertisements                 |
| Google Billing       | In-app purchases (Premium)     |
| Navigation Component | Fragment navigation            |
