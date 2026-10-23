# Semiotic Studio is now ABJEXT Studio

**The project has a new name and a new official home: [sxrvys/Abjext](https://github.com/sxrvys/Abjext).**

Same software, same development, new identity. We’re adopting **ABJEXT Studio** as the lasting name for the project. Thank you to everyone helping shape it through the beta.

## One final update here

**0.8.2 is the final transition release on this repository.** Existing Semiotic installations can find it through **Check for Updates**. That download installs **ABJEXT Studio**; once you open ABJEXT, all future update checks go exclusively to **[sxrvys/Abjext](https://github.com/sxrvys/Abjext)**.

[Download ABJEXT and read the current guide](https://github.com/sxrvys/Abjext) · [Final transition release and historical downloads](https://github.com/sxrvys/Semiotic/releases)

## Upgrade safely

1. Save your project and use **Semiotic → Check for Updates** to download the transition installer. You can also get it from Releases above.
2. Quit Semiotic, open the DMG, and drag **ABJEXT Studio.app** into **Applications**.
3. Open **ABJEXT Studio** and your saved project. Existing `.semiotic.json` files, presets, settings, and MIDI mappings remain compatible and in their existing locations.
4. Once you have confirmed the new app works, remove the old **Semiotic Studio.app** if desired and update your Dock shortcut. macOS may leave both apps installed because their names differ. **Do not delete your projects, source media, or application-support folders.**
5. Use **ABJEXT → Check for Updates** for future releases.

The legacy installer filename starts with `Semiotic-Studio-` so old updaters can recognize it. The app inside is **ABJEXT Studio**, identical to the app published in the new repository.

## Installation requirements

Apple Silicon (M1 or later), macOS 14 or later. All required app resources, including the VCR font, are bundled. No Python, pip, Terminal commands, separate codecs, or developer tools are needed. BlackHole is optional for routing live audio between applications.

These beta builds are locally signed but not yet Apple-notarized. If macOS cannot verify the developer, first try opening the app, then use **System Settings → Privacy & Security → Open Anyway**. See [Apple’s first-launch instructions](https://support.apple.com/102445). Do not disable macOS security protections; report a damaged-app or malware warning instead.

## Where to go next

- **Official releases, current documentation, changelog, and issue reports:** [ABJEXT](https://github.com/sxrvys/Abjext).
- This repository remains available for the transition installer and release history. No further feature updates are planned here.
- Both public repositories contain distribution documentation and binary releases only. Application source remains private.

Update checks and downloads remain manual and optional. No GitHub account or signup is required. The name change does not introduce licensing or tracking requirements.
