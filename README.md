# RAMUS

### Project by Vitaliy Yakovchuk

![Project Image](https://github.com/user-attachments/assets/72c8fcad-d8f1-4bc1-9186-ae4a1f1c9cf2)

**Java-based IDEF0 & DFD Modeler**

<img width="1792" alt="Screenshot 2019-11-18 at 11 14 26" src="https://user-images.githubusercontent.com/2261228/69039713-23c56d00-09f5-11ea-99c5-b6714efe3037.png">

<img width="1792" alt="Screenshot 2019-11-18 at 11 14 59" src="https://user-images.githubusercontent.com/2261228/69039723-27f18a80-09f5-11ea-9a8d-508069ce7bbd.png">

---

## How to Start the Application

### Step 1: Install JDK

Download and install the [Oracle JDK](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

### Step 2: Run the Application

In the console, navigate to the project folder and run:

```bash
./gradlew runLocal
```

### Step 3: Test the Application

#### For Linux (Tested on Ubuntu 20.04 and Fedora 34)

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/Vitaliy-Yakovchuk/ramus.git
   ```

2. **Navigate to the Project Folder:**

   ```bash
   cd ramus
   ```

3. **Run the Application:**

   ```bash
   ./gradlew runLocal
   ```

### Optional: Create a Shortcut to Launch the Application

1. Open your `.bash_aliases` file:
   ```bash
   nano ~/.bash_aliases
   ```

2. Add the following alias to easily launch the application:

   ```bash
   alias ramus='cd ~/path/to/ramus/folder/ && ./gradlew runLocal &'
   ```

3. Save the file and reload it:

   ```bash
   source ~/.bash_aliases
   ```

4. Now, you can simply run `ramus` in the terminal to launch the application.

# MacOS 

## Requirements (macOS)

- macOS with developer tools (preinstalled utilities: `sips`, `iconutil`).
- JDK 21+ with `jdeps`, `jlink`, and `jpackage` (full JDK, not JRE). For best results, install a standard Temurin/Oracle JDK.
- Optional (icon conversion fallback): `dwebp` from the `webp` package (e.g., `brew install webp`).

Tip: This project supports local overrides without changing your shell’s `JAVA_HOME`.

## Quick Start

1) Build a macOS .app for quick testing

```
./gradlew macosApp
```

2) Build a dmg for sharing

You can build a macOS DMG/App, by running:

```bash
./gradlew macosDmg
   ```

## Running From Source (Optional)

You can still run directly from sources:

```
./gradlew :local-client:runLocal
```

Note: the dev run uses your local Java installation; for the full native experience use the `.app` or DMG.

## Contributing

Contributions are very welcome—bug reports, macOS improvements, docs, and packaging tweaks. Please open issues or pull requests.

## What’s new in 2.0.2

- macOS app bundle and DMG packaging via Gradle + jpackage.
- Proper Dock icon and Info.plist; icons are sourced from `packaging/macos/AppIcon.appiconset` and converted to `.icns` during build (uses macOS `sips`/`iconutil`; falls back to `dwebp` if needed).
- Uses the macOS system menu bar (`apple.laf.useScreenMenuBar=true`).
- macOS keyboard shortcuts use the Command key (⌘) via the platform menu shortcut mask (e.g., ⌘S, ⌘O, ⌘Z, ⌘⇧S, etc.).
- Standalone distribution: bundles a Java runtime. Optionally uses `jlink` to create a minimized runtime; falls back to bundling the full JDK if `jlink` isn’t available.
- Modernized build/toolchain: project compiles for Java 17 (upstream used Java 8) and uses a recent Gradle (8.x). Packaging targets JDK 21 for the bundled runtime.
