# 🔥 FireSync – Google Sheets ↔ Firestore Sync Add-on

HMRUS LLC presents FireSync, a modular Google Sheets add-on enabling bi-directional syncing between Google Sheets tabs and Google Firestore collections.

Built for non-technical users — if a 3rd grader or a grandma can’t use it without knowing anything technical, we’ve failed.

----------------------------------------------------------------

## 🚀 Purpose

FireSync delivers a "just works" experience for syncing structured data between Google Sheets and Firestore — effortless, reliable, and low-friction.

----------------------------------------------------------------

## ✨ Key Features

- One-click setup via Google Sheets add-on
- Sync individual sheet tabs to Firestore subcollections
- Modular architecture for easy feature expansion
- Secure service account authentication (JWT & OAuth2)
- Real-time usage analytics shown in-app
- Predefined schema bootstrapping for quick start

----------------------------------------------------------------

## 🛠 Architecture Overview

Platform: Google Apps Script (Sheets Add-on)
Backend: Google Firestore (via REST API)
Auth: JWT signed with Utilities.computeRsaSha256Signature, exchanged for OAuth2 access token
Storage: ScriptProperties for private key storage

Firestore Structure (tree):
users/
  └── <userId> → email in `emailAddress`
sheets/
  └── <spreadsheetId>
      └── tabs/
          └── <tabId>
              └── rows/
                  └── <rowId>
config/
  └── global → environment config & feature flags

----------------------------------------------------------------

## Security (high level):
- Firestore security rules default to deny all
- HTTPS enforced for all requests
- Keys never exposed to end users

----------------------------------------------------------------

## 📊 Data & Privacy Summary

- We collect: Google account email, sheet/tab/row content you choose to sync, usage metrics (sync counts, API usage, data size)
- We don’t share: No personal or sheet content is shared with third parties. Only aggregated, non-identifiable totals may be used for reporting.
- Storage: Google Cloud Firestore (Google’s built-in security)
- Retention: No automatic deletion; you control your data lifespan.

For full details, see the Privacy Policy.

----------------------------------------------------------------

## 📬 Contact & Support

For support, feature requests, or privacy inquiries: firesyncdb@gmail.com
