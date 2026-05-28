# Workforce LMS - Deployment Guide

Version: 1.0  
Last updated: March 27, 2026

## 1. Overview

This guide covers deployment for:

- backend on Render
- database on MongoDB Atlas
- Android builds with Expo EAS
- Play Store preparation

## 2. Architecture

- Mobile app: Expo / React Native
- Backend: Node.js / Express
- Database: MongoDB Atlas
- Hosting: Render
- Push: Expo Notifications

## 3. Backend Deployment on Render

### Service settings

- Root directory: `backend`
- Build command: `npm install`
- Start command: `npm start`

### Required environment variables

- `MONGODB_URL`
- `JWT_SECRET`

### Recommended environment variables

- `APP_TIMEZONE=Asia/Kolkata`
- `UPLOAD_ROOT=/var/data/uploads`

### Screenshot to add

- Render web service settings
- Render environment variables page

## 4. MongoDB Atlas

Use Atlas for production database hosting.

### Check

- database user created
- IP/network access configured for Render
- correct connection string added to Render

### Screenshot to add

- MongoDB Atlas cluster overview
- Database connection screen

## 5. Mobile Environment

### Preview / production

Use Render backend in:

- `/Users/ajitkushwhaha/Developer/App/lms/mobile/eas.json`

### Local development

Use local backend in:

- `/Users/ajitkushwhaha/Developer/App/lms/mobile/.env`

## 6. Android Preview Build

Use internal preview builds for testing:

```bash
cd /Users/ajitkushwhaha/Developer/App/lms/mobile
npx eas-cli@latest build --platform android --profile preview
```

## 7. Android Production Build

Use production build for Play Store:

```bash
cd /Users/ajitkushwhaha/Developer/App/lms/mobile
npx eas-cli@latest build --platform android --profile production
```

Use:

- `.aab` for Play Store release
- `.apk` only for direct testing/distribution

### Screenshot to add

- EAS build success screen
- EAS artifacts page

## 8. Play Store Release

### Requirements

- Google Play Console account
- one-time registration fee
- app listing
- privacy policy URL
- data safety form

### Internal testing first

Recommended order:

1. Internal testing
2. Closed testing
3. Production

### Screenshot to add

- Play Console app dashboard
- Internal testing release screen

## 9. Privacy Policy

Public privacy policy page:

- `https://your-backend-domain/privacy-policy`

In this project:

- file:
  - `/Users/ajitkushwhaha/Developer/App/lms/backend/public/privacy-policy.html`
- backend route:
  - `/privacy-policy`

## 10. Data Safety

Likely declared data types:

- name
- email
- user ID / employee ID
- precise location
- photos
- device identifiers
- app activity
- leave reasons/comments
- notification token

## 11. iOS Note

Local iOS simulator/Xcode builds require macOS.

Windows limitations:

- cannot run Xcode
- cannot run iOS simulator

Alternative:

- use EAS cloud iOS builds
- requires Apple Developer account

## 12. Release Checklist

Before release:

- backend is deployed and healthy
- mobile points to production API
- login works
- attendance works
- leave works
- push notifications work
- privacy policy URL is public
- data safety form is completed
- screenshots are ready

## 13. Client Handover Checklist

Provide client with:

- Employee Guide PDF
- Admin Guide PDF
- privacy policy URL
- Play Store testing link
- support contact email
