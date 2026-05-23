# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

Expo (React Native) + TypeScript cross-platform mobile app. Targets iOS App Store and Android Google Play. Bootstrapped with Expo SDK 52 and React Native 0.76.

## Development commands

```bash
npm start          # Start Expo dev server
npm run android    # Start with Android emulator
npm run ios        # Start with iOS simulator
npm run web        # Start web version
npm run lint       # ESLint across all .ts/.tsx files
npm run format     # Prettier formatting
npm run typecheck  # TypeScript type checking (no emit)
```

Run a single file's type errors: `npx tsc --noEmit --pretty <path>`

## Architecture

```
src/
  components/    Reusable UI components
  screens/       Full screen-level components
  navigation/    React Navigation config and navigators
  hooks/         Custom React hooks
  utils/         Pure utility functions
  types/         Shared TypeScript type definitions
  constants/     App-wide constants (strings, config values)
  services/      API clients, external service wrappers
App.tsx          Root component (entry point)
app.json         Expo configuration (app name, icons, bundle IDs)
```

Current package IDs: `com.mashaojie.claudecodetest` (Android) / same as bundle identifier (iOS).

## Code style

- TypeScript strict mode enabled
- Prettier: single quotes off, trailing commas all, 100 print width
- ESLint: flat config (`eslint.config.mjs`) with TypeScript and React plugins
- No PropTypes needed — use TypeScript interfaces (rule disabled)
