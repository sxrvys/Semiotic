# Semiotic Studio

**Edit a video. Play it like an instrument.**

Semiotic Studio is a native Mac application for experimental music videos, glitch art, and live visual performance. It brings a multitrack timeline, a playable clip sampler, and a video effects and synthesis engine into one workspace.

Build precise edits, layer and distort footage, map visual parameters to music or MIDI, and record a pad performance back into an editable timeline. From restrained processing to harsh feedback and rhythmic noise, the emphasis is on making the picture something you can perform.

**[Download beta builds](https://github.com/sxrvys/Semiotic/releases)** · **[Report an issue](https://github.com/sxrvys/Semiotic/issues)**

This repository hosts beta installers, release notes, and user documentation. Application source is maintained separately. Semiotic is under active development; save a copy of important projects before trying a new beta.

## Requirements

- An **Apple Silicon Mac**: M1, M2, M3, or newer.
- **macOS 14 Sonoma or later**, unless an individual release specifies a newer requirement.
- Your own video and audio files. A MIDI controller is optional.

No Terminal commands, Python, pip, Xcode, TouchDesigner, Max, Ableton, or additional codec package are required. The app includes its resources and uses the media and graphics frameworks supplied with macOS. BlackHole is optional for routing audio from another application into Semiotic's visual reactivity controls; ordinary editing, playback, export, MIDI, and soundtrack reactivity work without it.

## Install

1. Open **[Releases](https://github.com/sxrvys/Semiotic/releases)** and choose the newest beta. Download the file ending in **`AppleSilicon.dmg`** under Assets. GitHub's automatic “Source code” archives are not the application.
2. Open the DMG and drag **Semiotic Studio.app** onto **Applications**.
3. Eject the DMG and open Semiotic Studio from Applications.
4. If macOS says the developer cannot be verified, first attempt to open the app, then go to **System Settings → Privacy & Security → Open Anyway** and confirm. These beta builds are locally signed but are not yet notarized by Apple. Only approve an installer from this repository or the developer.

If macOS instead reports malware or a damaged application, keep the warning intact and report the exact message. You do not need to disable Gatekeeper or run a quarantine-removal command. See [Apple's instructions for opening an app from an unidentified developer](https://support.apple.com/102445).

Allow access to folders containing your media when macOS asks. Microphone permission is needed only when using live audio input, including a virtual audio device.

## Stay current

In a build with the updater, open **Settings → Updates → Check for Updates**, or choose **Semiotic Studio → Check for Updates…** from the menu bar.

Read the release notes and choose **Download DMG…**. Semiotic downloads the installer directly and verifies its size and SHA-256 checksum before saving it. Use **Show Installer in Finder** when it is ready.

Save your project, quit Semiotic, then open the DMG and replace the older copy in Applications. Your project files, source media, and saved preferences remain in their existing locations. A new beta may need macOS approval again. Older builds without the updater can download directly from Releases.

Update checks and installation are **manual and optional**. No GitHub account, signup, or background update service is required. The updater sends no project or media data. GitHub receives the ordinary network request needed to check or download a release.

## First session

1. Choose **New Project** on the welcome screen or in the File menu.
2. Use **Import Clips…** or drag video and music from Finder into **Project Media**. The bin's **+** button opens your configured source library in Finder.
3. Drag footage onto a video track and music onto an audio track. Selecting a bin thumbnail while transport is stopped lets you preview that source in the main player.
4. Press **Space** to play or pause. Drag the playhead to scrub; use the arrow keys for frame-accurate positioning.
5. Open **Effects**, add an effect, and raise its Mix or Amount. New projects start with a clean image. **Color** provides a separate neutral grading panel.
6. Save the project with **⌘S**. Use **Export Mix…** for a finished movie.

Project files use readable **`.semiotic.json`**. Source media stays in its original location, so keep those files available when reopening or moving a project.

## Editor workspace

- **Multitrack editing:** video and independent audio tracks; trim, split, move, duplicate, copy/paste, ripple delete, and group editing.
- **Timing:** clip speed and reverse, Shift-drag rate stretching, beat grid, tap tempo, and video quantization. Video edits do not automatically rearrange your audio.
- **Compositing:** stacked clips, blend modes, opacity, split-screen placement, track visibility/solo/lock, and dedicated mask clips.
- **Automation:** editable parameter envelopes, audio-reactive mappings, and recorded control changes. Arm the relevant Write controls when recording parameter or macro automation.
- **Color and effects:** neutral grading plus global or per-clip FX chains. Reorder effects, save individual presets, and save complete Looks and playable racks.
- **Monitoring:** adjustable preview quality, a larger popout preview, and fullscreen output to an available secondary display.

Dragging a clip edge normally trims or reveals source material. **Shift-drag the edge** to stretch its duration and change playback rate. Audio stretching offers **Vinyl** (speed and pitch together) and **Tempo** (preserve pitch) modes.

## Performance workspace

Switch to **Performance** to play clips from the pad grid while keeping the timeline available for editing.

- Drag a Project Media thumbnail onto a pad to assign it. Use Gate, Toggle, or One shot behavior to suit the clip.
- Ten pad banks provide space for clips and assignable performance actions.
- Eight macros can control individual FX parameters or combinations of parameters. Save a rack to reuse a setup.
- Use the performance **Record** control to write pad performances into the timeline for later editing and quantization.
- Explore the step sequencer for rhythmic clip patterns and gate lengths.
- Open **Settings → Control Surfaces** to enable MIDI and select a detected input. The SP-404MKII setup provides clip triggering and performance controls; generic MIDI Learn supports other controllers.
- Use **MIDI Map** in the top toolbar, click a highlighted software control, then move or press the hardware control you want to assign. Existing assignments are preserved unless explicitly changed. Settings retain the selected controller and saved mappings.

Pad-bank and knob behavior depends on the controller profile and your mappings. Check the on-screen labels when changing macro pages or assigning utility pads.

## Effects and video synthesis

The toolbox includes delay and feedback, reverse and stutter processing, gated tremolo, CRT and tape character, dithering, colorization, spatial distortion, kaleidoscopic geometry, and flipbook-style animation.

The synthesis tools extend that into **Raster Synth**, scan-line displacement, **Video FM**, **Wavefolder**, **Ring Modulator**, **Polar Oscillator**, **Vector Scope**, **Clocked Noise**, and **Video Logic Mixer**. Combine oscillators, beat-clocked patterns, masks, and footage into shifting textures and geometry. Factory presets and playable racks offer starting points; individual controls remain available for automation, MIDI, and audio modulation.

**All FX process video only.** Audio tracks keep their own editing, level, and stretch controls.

For music-driven visuals, start with the timeline soundtrack, then use **Map** beside an FX parameter to assign level, bass, mids, or highs. Adjust the mapping range and input sensitivity. Live input from BlackHole or another audio device is a secondary option for following Ableton or another application.

## Default shortcuts

These are the factory bindings. Timeline commands apply when you are editing the timeline, not typing into a text field. Customize them in **Settings → Shortcuts**; the Timeline menu shows current bindings.

### Transport and navigation

| Action | Shortcut |
| --- | --- |
| Play / Pause | Space |
| Stop | Enter |
| Return playhead and timeline view to the beginning | Enter twice |
| Shuttle backward / stop / forward (silent) | J / K / L |
| Previous / next frame | ← / → |
| Back / forward ten frames | Shift + ← / → |
| Previous / next cut | ↑ / ↓ |
| Previous / next beat division | [ / ] |
| Zoom in / out | = / − |
| Fit entire timeline | Shift + Z |
| Zoom to selection | Option + Z |
| Match frame in source viewer | F |

### Editing and timing

| Action | Shortcut |
| --- | --- |
| Split at playhead | ⌘B |
| Delete selected clips, leaving a gap | Delete |
| Ripple delete on selected tracks | Shift + Delete |
| Duplicate selection | ⌘D |
| Copy / Cut / Paste at playhead | ⌘C / ⌘X / ⌘V |
| Paste video attributes | ⌘Shift + V |
| Select all clips | ⌘A |
| Undo / Redo | ⌘Z / ⌘Shift + Z |
| Nudge selection one frame | Option + ← / → |
| Nudge selection ten frames | Option + Shift + ← / → |
| Nudge selection one beat division | Option + [ / ] |
| Toggle snapping | S |
| Quantize video | Shift + Q |
| Set work-range In / Out | I / O |
| Go to range In / Out | Shift + I / O |
| Clear work range | Option + X |
| Loop selection | ⌘L |
| Add marker | M |
| Selection / Slip / Roll tool | V / Y / R |

Ripple delete removes the selected material and closes its gap on the affected tracks. Quantization uses the project's tempo and chosen beat division; it does not analyze the musical intention of each cut. Preview the result and undo if needed.

### Projects and mouse gestures

| Action | Shortcut or gesture |
| --- | --- |
| New / Open project | ⌘N / ⌘O |
| Save / Save As | ⌘S / ⌘Shift + S |
| Import clips | ⌘I |
| Settings | ⌘, |
| Quit | ⌘Q |
| Scrub | Drag the playhead |
| Rate stretch | Shift-drag a clip edge |
| Zoom timeline | Trackpad pinch |
| Larger preview window | Double-click the preview |
| Add or manage tracks | Timeline + or track context menu |

## Media and export

Common verified inputs include **H.264 MP4/MOV**, **HEVC MOV**, and **ProRes 422 MOV**, plus **MP3, WAV, FLAC, AIFF, AAC/M4A, ALAC/M4A, and CAF** audio. Import uses macOS decoders and checks the actual file; an extension alone does not guarantee compatibility. DRM-protected files are unsupported.

**Export Mix** produces **H.264 MP4**, with **AAC audio** when included. Choose 720p, 1080p, or 4K-class resolution; 30 or 60 fps; and landscape, square, or portrait framing. Instagram-oriented presets are included. Export renders the original sources at the chosen output size, independently of the lighter interactive preview.

The current pipeline targets SDR Rec.709 delivery. ProRes export, transparent video export, exact cinema/broadcast frame rates, and HDR mastering are not currently offered. For unsupported input, convert to H.264 MP4, ProRes MOV, or PCM WAV before importing.

For lighter machines, start with **360p preview**, shorter feedback/rewind histories, and fewer simultaneous layers. Use 720p preview when judging fine masks and texture. Live capture follows preview quality; use Export Mix for delivery resolution.

## Feedback

Found a problem or an awkward workflow? [Open an issue](https://github.com/sxrvys/Semiotic/issues) with:

- Semiotic's version and build number from About or Settings → Updates.
- Your Mac model and macOS version.
- Steps to reproduce, what you expected, and what happened.
- A screenshot or a short sample you have permission to share, if helpful.

Issues here are public. Avoid posting client footage, private project paths, or other confidential material. Small reproducible examples are especially useful during the beta.
