# Expo Build Tools

### 🧩 Local builds

```bash
# Development build (debug with dev client)
npx expo run:android
# or
npx expo run:ios
```

```bash
# Production build (local)
npx expo build:android --type app-bundle
# or
npx expo build:android --type apk
```

---

### ☁️ Cloud builds (EAS)

```bash
# Development (internal testing)
eas build --profile development --platform android
```

```bash
# Preview build (APK for testing)
eas build --profile preview --platform android
```

```bash
# Production release (AAB for Play Store)
eas build --profile production --platform android
```
