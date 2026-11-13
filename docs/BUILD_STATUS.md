# Build Status

## Current status

The public GitHub repository has been created and is public. It contains a product handoff and an icon concept, but no app source yet.

The current Replit project already contains its single permitted Expo mobile artifact for Leo’s private app. Replit rejected creating a second mobile artifact in the same project. Continue this public app in a dedicated Replit project imported from this repository; do not replace or merge with Leo’s private app.

## Known integration blockers

- Memory Machine uses user-scoped OAuth with PKCE S256, but its current OAuth client validation only accepts Grok/xAI. The service owner must register/support the CrAIshPad native client before the app can connect.
- The AIs and Ears public API documentation has not been provided.
- Until those contracts are available, build local continuity and the model-provider connection independently; do not claim either service is live.

## Initial implementation assumptions

- Expo + TypeScript.
- Local-first app data using AsyncStorage.
- User-specific model key in SecureStore.
- No app-owned shared provider secret, no user database, and no push notifications in the first build.
- User-managed persona and memories; the app does not author a hidden persona prompt.
