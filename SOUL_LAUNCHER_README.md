# Soul Launcher — custom build notes

This source tree is rebranded as **Soul Launcher** with a black/aqua visual identity.

## Included changes
- Launcher display name and visible branding changed to **Soul Launcher**.
- Launcher icon and in-app logo use the supplied Soul mark with the word **CLIENT** removed.
- Main accent palette changed to aqua (`#00E5D4`) on dark/black surfaces.
- About page lists **7xPojav_** as the sole developer; upstream PojavLauncher and Amethyst lineage/credits remain acknowledged.
- The bundled client catalog exposes only **Soul for Minecraft Java 1.21.11**.
- The supplied `SoulClient-1.21.11.jar` is bundled unchanged and verified by SHA-256 during installation.

## Build
Open this folder in Android Studio with Android SDK/NDK installed, allow Gradle to download its wrapper/dependencies, then build the `app_pojavlauncher` debug or release variant.

Command-line debug build:

```bash
./gradlew :app_pojavlauncher:assembleDebug
```

The build was not executed in the preparation environment because the Gradle 8.13 wrapper distribution could not be downloaded (network DNS unavailable) and no Android SDK path was configured. XML and JSON resource files were parsed successfully; this is not a claim of a completed APK build.

## Notes
- The launcher keeps the upstream application ID to avoid unrelated package migration changes.
- The upstream release signing keystore was intentionally excluded; configure your own signing key with Gradle properties before making a signed release.
- Existing upstream license/NOTICE files are retained. The supplied Soul client JAR is included as provided and is not modified.
