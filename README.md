# My-prompt-app

A mobile-first, serverless web application for building, managing and synchronizing AI prompts

## 🚀 Core Features
* **Mobile-Optimized UI:** Deep navigation architecture supporting Android hardware back-buttons via History API.
* **Smart Generator:** Automatically formats prompts based on tag weights (e.g., `(cyberpunk:1.5), neon`).
* **Offline-First:** Runs entirely on `LocalStorage`. Fast, private, and requires zero loading screens.
* **Sync on Demand:** Cloud synchronization across devices using Firebase Firestore.
* **Conflict Resolution:** Uses Timestamp-based LWW (Last Write Wins) and Atomic Transactions to merge data safely.
* **Tombstone & Purge:** Employs soft-deletes to prevent cross-device data resurrection, with a manual Purge function to hard-delete and optimize storage.
* **Bulk Import:** Rapidly add hundreds of tags using raw text (`# Group Name \n Tag`).

## 🛠 Technical Stack
* **Frontend:** Vanilla HTML5, CSS3, JavaScript (ES6 Modules). No frameworks (React/Vue) to ensure maximum performance and portability in a single file.
* **Backend/Database:** Firebase Firestore (Free Tier).

## ⚙️ Setup & Deployment
1.  Save the source code as `index.html`.
2.  Open it directly in any modern browser (Chrome, Edge, Safari).
3.  *(Optional for Mobile)* Host the file on GitHub Pages to access it via your phone and "Add to Home Screen".

## ☁️ Firebase Configuration (Optional)
To enable Cloud Sync across devices:
1.  Create a project on [Firebase Console](https://console.firebase.google.com/).
2.  Register a Web App and copy the `firebaseConfig` object into the `index.html` file.
3.  Create a Firestore Database.
4.  Update Firestore Security Rules to allow access to the specific document ID used in the app.

## ⚠️ Known Limitations
* **Storage Quota:** Browsers limit `LocalStorage` to ~5MB. While sufficient for tens of thousands of tags, clearing browser data will permanently erase unsynced local data.
* **Security by Obscurity:** The cloud sync relies on a static, hardcoded Document ID rather than full Authentication. It is designed for personal use, not public multi-user deployment.
