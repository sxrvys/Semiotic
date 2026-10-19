# Semiotic Studio

**Edit a video. Play it like an instrument.**

Semiotic Studio is a native Mac application for experimental music videos, glitch art, and live visual performance. It brings a multitrack timeline, a playable clip sampler, and a video effects and synthesis engine into one workspace.

Build precise edits, layer and distort footage, map visual parameters to music or MIDI, and record a pad performance back into an editable timeline. From restrained processing to harsh feedback and rhythmic noise, the emphasis is on making the picture something you can perform.

**[Download beta builds](https://github.com/sxrvys/Semiotic/releases)** · **[Report an issue](https://github.com/sxrvys/Semiotic/issues)**

This repository hosts beta installers, release notes, and user documentation. Application source is maintained separately. Semiotic is under active development; save a copy of important projects before trying a new beta.

## Changelog

### 0.5.0 beta — October 19, 2026

- Unified Timeline / Sequencer workspace with independent Media, Pads, FX, Macros, and Automation visibility. Common project, export, and capture actions live in File; source/canvas setup lives in Settings.
- Sequencer lanes in the main working area, with step controls in the left sidebar. Drag lane headers to reorder; layer routing and playback order stay intact. Pattern creation/duplication, chaining, Fill, Store/Mutate/Restore, probability, weighted clip choices, retriggers, and parameter locks support repeatable performances.
- Contextual **Clip inspector** for timeline clips, media-source defaults, pads, and clip-lane steps. Add scale, position, rotation, flips, transparent edge cropping, and multiline text with installed fonts, color, alignment, wrapping, opacity, outline, and background.
- Source defaults are copied into new placements. Individual clip/pad/step changes remain independent; sequencer capture and Place Pattern retain their appearance. Text can be placed before or after clip FX; global FX always process the composite.
- Weighted clip choices now live in a collapsed **Timing → Random clip choices** section, leaving Timing, FX, and Lane as the main step tabs.
- Welcome-screen focus cleanup, visual-only undo for framing/text, and cached text rendering at preview/export resolution.
- Project format 16 preserves the new appearance fields. Existing projects open; projects saved in this version require an updated app. Keep a copy if returning to an older beta.

This release includes changes developed since the public 0.2.0 beta. The macro rack remains collapsible with **Macros**; its sizing behavior is unchanged.

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
2. Use **File → Import Media…** or drag video and music from Finder into **Project Media**. The bin's **+** button opens your configured source library in Finder.
3. Drag footage onto a video track and music onto an audio track. Selecting a bin thumbnail while transport is stopped lets you preview that source in the main player.
4. Press **Space** to play or pause. Drag the playhead to scrub; use the arrow keys for frame-accurate positioning.
5. Open **Effects**, add an effect, and raise its Mix or Amount. New projects start with a clean image. **Color** provides a separate neutral grading panel.
6. Save the project with **⌘S**. Use **File → Export Mix… (⇧⌘E)** for a finished movie.

Project files use readable **`.semiotic.json`**. Source media stays in its original location, so keep those files available when reopening or moving a project.

## Unified workspace

**Timeline / Sequencer** switches the lower working view without stopping playback. **Media**, **Pads**, and **FX** toggle independently in the top toolbar. **Macros** and **Automation** open above/below the working view. Macros and automation take turns in the detail space so the working area stays usable. **Focus** collapses the browser and inspector while keeping pads available; panel visibility is remembered. Source and canvas controls live in **Settings → General**. Project actions, export, and preview capture live in **File**.

### Editing

- **Multitrack editing:** video and independent audio tracks; trim, split, move, duplicate, copy/paste, ripple delete, and group editing.
- **Timing:** clip speed and reverse, Shift-drag rate stretching, beat grid, tap tempo, and video quantization. Video edits do not automatically rearrange your audio.
- **Compositing:** stacked clips, blend modes, opacity, split-screen placement, track visibility/solo/lock, and dedicated mask clips.
- **Automation:** editable parameter envelopes, audio-reactive mappings, and recorded control changes. Arm the relevant Write controls when recording parameter or macro automation.
- **Color and effects:** neutral grading plus global or per-clip FX chains. Reorder effects, save individual presets, and save complete Looks and playable racks.
- **Monitoring:** adjustable preview quality, a larger popout preview, and fullscreen output to an available secondary display.

Dragging a clip edge normally trims or reveals source material. **Shift-drag the edge** to stretch its duration and change playback rate. Audio stretching offers **Vinyl** (speed and pitch together) and **Tempo** (preserve pitch) modes.

### Crop, transform, and text

Open **FX → Clip** in the right inspector, then select the video you want to edit. The **Editing** selector identifies the current target: Timeline, Media, Pad, or Step.

- **Media:** set source defaults before placement. New timeline clips and newly assigned pads copy these settings; existing placements stay unchanged.
- **Timeline:** edit selected clips. Multi-selection patches the control you changed while preserving each clip’s other settings. Split, duplicate, copy/paste, and project save retain the appearance.
- **Pad:** adjust that pad’s source snapshot without changing the original media-pool item.
- **Step:** override framing/text for a clip-lane hit, including clips selected from a weighted pool. **Use source framing & text** restores inheritance. Play the sequence to see a step’s settings.

Expand **Transform & Crop** for scale, X/Y, rotation, flips, and frame-edge cropping. Position and crop values are normalized to the canvas; crop happens before transform. Transparent areas reveal lower video tracks. These are numeric/slider controls; direct on-preview transform handles are not included in this beta.

Expand **Text** to enter multiline text and choose an installed font, size, color, alignment, position, wrapping width, opacity, black outline, and black background. System Bold is the default. Missing fonts fall back to the system font; fonts are not embedded in project files. Text is attached to its clip or step gate. For a title during only part of a timeline clip, split that section and add text to that fragment. Standalone title tracks and phrase sequencing are not included in this beta.

**Send text through clip FX** puts typography into the clip processing chain. Leave it off for text after clip FX; global FX still affect the complete image. Source audition shows framing and text; it does not apply timeline/global FX. All edits are nondestructive.

### Playing clips and sequences

Open **Pads** and **Macros** to play clips while keeping either the timeline or sequencer available. There is no separate Performance mode.

- Drag a Project Media thumbnail onto a pad to assign it. Use Gate, Toggle, or One shot behavior to suit the clip.
- Ten pad banks provide space for clips and assignable performance actions.
- Eight macros can control individual FX parameters or combinations of parameters. Save a rack to reuse a setup.
- Use the performance **Record** control to write pad performances into the timeline for later editing and quantization.
- Play two independent live layers. Choose **A** or **B** before triggering a pad, or assign a fixed layer in Pad Settings. Each has its own FX rack, opacity and blend mode. Center on the crossfader keeps both available for blending; either end isolates that layer.
- Layer **FX** opens its own rack. Global FX process the combined picture. MIDI Map can assign layer parameters, opacity, the crossfader, or scene recall without replacing existing SP-404 mappings.
- **Scenes** saves named snapshots of clip assignments, both layers, the global rack and macros, and the selected pattern. Recall uses the Launch interval while playing; new pad hits use the recalled assignments. Recorded scene changes replay on the timeline and can be edited in Scenes → Recorded rack changes.
- **Sequencer** opens the step lanes in the timeline area, keeping the preview visible. Start with two clip rows, a mask row, and an FX row; expand to eight independent rows with 1–64 steps each.
- **Reorder sequencer lanes:** drag the entire lane header (the “Clips A / Drop a clip here” box) onto another header, or right-click it and choose **Move Up / Move Down**. The row’s clips, steps, masks and FX move together; its assigned layer and playback stay unchanged. Order is saved with the project and supports undo. Audio is arranged in **Timeline** and continues playing with the sequencer. Select a step to edit its **Timing / FX / Lane** controls in the left sidebar beneath Media and Pads.
- **Media** and **FX** in the top toolbar collapse independently. **Focus** above the working view hides both; **Restore panels** brings back the previous combination. The divider above the performance controls adjusts preview versus sequencer height.
- Drag Project Media or a pad onto a lane to choose its source, or onto a step to assign a different clip. Click empty steps to add hits; select a lit step to edit it, then click it again to disable it. The left sidebar holds Timing, FX, and Lane controls. Weighted clip pools are available under **Timing → Random clip choices**.
- Steps support weighted clip pools, probability, gate length, retriggers, frame-aligned microtiming, per-step source starts, first/every-N/previous-result conditions, and Fill. Mask and FX rows can run at different lengths from the clip rows.
- FX steps can gate an effect or saved chain and lock individual parameters without retriggering the footage. Use **Use for lane** to give new steps the same default FX assignment.
- Hold **Fill**, or enable **Latch**, for Fill-only steps. **Store → Mutate → Restore** offers a reversible way to try variations. These performance buttons can be assigned through MIDI Map without changing existing controller mappings.
- **Place Pattern** generates a traversal using the saved seed/current Fill state. **Record** captures the actual live choices; stopping places editable clips, masks, and FX automation on the timeline. Probability never rerolls a recorded take during export.
- Open **Settings → Control Surfaces** to enable MIDI and select a detected input. The SP-404MKII setup provides clip triggering and performance controls; generic MIDI Learn supports other controllers.
- Use **MIDI Map** in the top toolbar, click a highlighted software control, then move or press the hardware control you want to assign. Existing assignments are preserved unless explicitly changed. Settings retain the selected controller and saved mappings.

Pad-bank and knob behavior depends on the controller profile and your mappings. Check the on-screen labels when changing macro pages or assigning utility pads.

## Effects and video synthesis

The toolbox includes delay and feedback, reverse and stutter processing, gated tremolo, CRT and tape character, dithering, colorization, spatial distortion, kaleidoscopic geometry, and flipbook-style animation.

The synthesis tools extend that into **Raster Synth**, scan-line displacement, **Video FM**, **Wavefolder**, **Ring Modulator**, **Polar Oscillator**, **Vector Scope**, **Clocked Noise**, and **Video Logic Mixer**. Combine oscillators, beat-clocked patterns, masks, and footage into shifting textures and geometry. Factory presets and playable racks offer starting points; individual controls remain available for automation, MIDI, and audio modulation.

**Effects, chains, racks, and macros:** an effect is one processor; a chain is the ordered collection of processors. **Save Rack…** stores the chain together with its macro assignments and envelopes. **Saved Racks…** recalls that setup, adds the complete chain as one FX slot, or assigns it to one macro. A macro is a playable control that moves one or several parameters. **Save FX Preset…** stores only the selected effect. These controls are in the Effects inspector; **Racks** above the working view also offers factory performance setups.

**All FX process video only.** Audio tracks keep their own editing, level, and stretch controls.

For music-driven visuals, start with the timeline soundtrack, then use the **music-note button** beside an FX parameter to assign level, bass, mids, or highs. Set the response range in that popup; choose the audio source and global sensitivity in **Settings → Audio**. The same popup offers beat, oscillator, and random modulation. Live input from BlackHole or another audio device is a secondary option for following Ableton or another application.

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

**Export Mix** produces **H.264 MP4**, **ProRes 422 MOV**, or **ProRes 422 HQ MOV**, with **AAC audio** when included. Choose 720p, 1080p, or 4K-class resolution; 23.976, 24, 25, 29.97, 30, 50, 59.94 or 60 fps; and landscape, square, or portrait framing. Instagram-oriented presets are included. Export renders the original sources at the chosen output size, independently of the lighter interactive preview.

The current pipeline targets SDR Rec.709 delivery. Transparent video export and HDR mastering are not currently offered. ProRes files are larger than H.264 files. For unsupported input, convert to H.264 MP4, ProRes MOV, or PCM WAV before importing.

**Capture Preview** records the processed preview plus the timeline soundtrack. Enable or disable audio in **Settings → Export**. Pauses and seeks are captured; finishing streams the retained soundtrack into the movie. Live input drives visual reactivity; record it onto an audio track first if you want it included. Video effects never process audio.

For lighter machines, start with **360p preview**, shorter feedback/rewind histories, and fewer simultaneous layers. Use 720p preview when judging fine masks and texture. Live capture follows preview quality; use Export Mix for delivery resolution.

## Feedback

Found a problem or an awkward workflow? [Open an issue](https://github.com/sxrvys/Semiotic/issues) with:

- Semiotic's version and build number from About or Settings → Updates.
- Your Mac model and macOS version.
- Steps to reproduce, what you expected, and what happened.
- A screenshot or a short sample you have permission to share, if helpful.

Issues here are public. Avoid posting client footage, private project paths, or other confidential material. Small reproducible examples are especially useful during the beta.
