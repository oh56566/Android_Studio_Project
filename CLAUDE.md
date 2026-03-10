# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build Commands

```bash
# Build debug APK
./gradlew assembleDebug

# Build release APK
./gradlew assembleRelease

# Run unit tests
./gradlew test

# Run a single unit test class
./gradlew test --tests "com.example.myapplication.ExampleUnitTest"

# Run instrumented (Android) tests (requires connected device/emulator)
./gradlew connectedAndroidTest

# Clean build
./gradlew clean

# Install debug APK on connected device
./gradlew installDebug
```

## Project Structure

Single-module Android app (`app/`) with:
- `app/src/main/java/com/example/myapplication/` — Kotlin source files
- `app/src/main/res/` — Resources (layouts, drawables, values)
- `app/src/test/` — JUnit unit tests
- `app/src/androidTest/` — Espresso instrumented tests
- `gradle/libs.versions.toml` — Version catalog for all dependencies

## Tech Stack

- **Language**: Kotlin
- **Min SDK**: 29, **Target SDK**: 36, **Compile SDK**: 36 (minor API level 1)
- **AGP**: 9.0.1
- **UI**: XML layouts with `ConstraintLayout`, Material Components
- **Entry point**: `MainActivity` (AppCompatActivity with edge-to-edge enabled)
- **Test frameworks**: JUnit 4 (unit), Espresso (instrumented)

## Architecture

This is a freshly scaffolded single-Activity app. `MainActivity` sets up edge-to-edge display and applies system bar insets padding. No architecture pattern (MVVM, MVI, etc.) has been established yet — add one before building significant features.

All dependency versions are managed centrally in `gradle/libs.versions.toml`. Add new dependencies there rather than hardcoding versions in `app/build.gradle.kts`.