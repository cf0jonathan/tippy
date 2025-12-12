# Tippy — Tip Calculator

## Overview
A small Android tip calculator app (Kotlin/Java, Gradle) that computes tip amount, total bill, and per-person share. The UI uses ConstraintLayout and provides SeekBars for tip percentage and people count so users can quickly explore how tip and splitting affect the bill.

## Enhancements
- Tip percentage SeekBar with live percentage display (`seekBarTip`, `tvTipPercent`).
- People splitter SeekBar with live people count (`seekBarPeople`, `tvPeopleCount`) and per-person amount (`tvPerPersonAmount`).
- Large, clear displays for tip amount and total (`tvTipAmount`, `tvTotalAmount`).
- Decimal input for bill amount (`etBaseAmount`) with hint and `inputType="numberDecimal"`.
- Clean responsive layout using `ConstraintLayout` and sensible `tools:` preview values.
- View IDs prepared for easy wiring to Kotlin/Java logic (supports ViewBinding or `findViewById`).

## Setup & Run (Windows - CMD)

Prerequisites
- Windows machine with Android Studio (recommended).
- JDK and Android SDK installed and configured.
- Emulator or physical Android device connected (for instrumented tests / running app).

Clone the repository

```cmd
git clone <repo-url>
cd tippy
```

Open in Android Studio
- `File > Open` and select the project root folder. Let Gradle sync finish.

Build from command line (Windows CMD)

```cmd
REM Build debug APK
.\gradlew assembleDebug

REM Run unit tests
.\gradlew test

REM Run instrumented tests on connected device/emulator
.\gradlew connectedAndroidTest
```

Install / Run the app

```cmd
REM Install the debug APK to a connected device/emulator
adb install -r app\build\outputs\apk\debug\app-debug.apk
```

Or run from Android Studio: select a device and click Run.

Notes & Implementation tips
- The tip SeekBar `max` is `30` (representing 0–30%).
- The people SeekBar `max` is `19` with initial `progress="0"` — treat people as `progress + 1` (so 0 => 1 person).
- Use ViewBinding or `findViewById` to wire the UI IDs found in `app/src/main/res/layout/activity_main.xml` to your activity logic.

Usage
- Enter the bill amount in the `Base` field.
- Adjust the `Tip` SeekBar to change tip percentage and see `Tip` and `Total` update live.
- Adjust the `People` SeekBar to split the bill and see `Per Person` amount.

Author
- Made quickly by Jonathan (original UI & layout present in the repo).

If you'd like, I can also add a brief `MainActivity.kt` implementation that wires the UI to live calculations and unit tests for the calculation logic. Want me to add that next?
