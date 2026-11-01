# SimpleCamPTZ community testing downloads

SimpleCamPTZ is a native OBS plugin for manual PTZ camera control and scene-triggered preset recall, with a dockable or floating control window.

## Downloads

Both versions are community testing pre-releases. Choose the version for your testing needs, then download the **AllFourInstallers ZIP** under its Assets.

| Version | Purpose |
| --- | --- |
| [v0.2.0](https://github.com/wzaggle/SimpleCamPTZ-Releases/releases/tag/v0.2.0) | Existing community-testing baseline for VISCA cameras; maintainer reports installation and camera operation on all four platforms. |
| [v0.2.1](https://github.com/wzaggle/SimpleCamPTZ-Releases/releases/tag/v0.2.1) | Adds experimental HTTP transport with Panasonic AW command handling, plus a **draft, hardware-untested AW-HE130 profile**. |

Each ZIP includes Windows x64, Intel Mac, Apple Silicon Mac and Ubuntu 24.04 native OBS packages, installation instructions, the illustrated User Guide PDF, quickstart, release notes, Camera Profiler guide and feedback template. Mac packages are ad-hoc signed and not notarized, require macOS 13+ and must match OBS architecture. Ubuntu packages target native OBS 32+ on Ubuntu 24.04 x64, not Flatpak or Snap. Windows is x64 only.

The illustrated PDF covers the v0.2.0 baseline. The v0.2.1 ZIP adds **PANASONIC-TESTING-v0.2.1.md**; that guide and the draft profile JSON are also separate release assets.

## Panasonic testing in v0.2.1

This release adds two distinct pieces: the HTTP/Panasonic AW method shared by Camera Profiler and normal camera control, and the AW-HE130 model profile containing commands, ranges and tuning. Existing raw VISCA/TCP, raw UDP and Sony-framed UDP methods remain available.

Open the bundled Panasonic profile in Camera Profiler, enter the camera’s numeric IPv4 address and begin with **Test HTTP** and individual power, zoom and position inquiries. Follow the testing guide before movement or preset writes. Profiler Send is not a timed jog: explicitly send the matching STOP command. Use **Save trace** to export results. Test All and automatic zoom discovery are disabled for this method.

Plain HTTP only: **credential entry and TLS are not implemented**. HTTP 401/403 is reported as an access failure. The draft defaults are port 80, request gap 150 ms (minimum 130 ms) and reply timeout 3000 ms. Valid AW replies confirm command acceptance, not completed movement. Real-camera directions, STOP and limits still require testing.

All four v0.2.1 native builds passed all 12 automated test suites from the same source revision. Simulator tests do not establish AW-HE130 compatibility or replace manual OBS/hardware testing.

## Community testing pre-release

The goal of 0.2.x is user feedback, problem reports and new camera profiles backed by real hardware testing. Existing bundled profiles cover AViPAS AV-1280W over raw VISCA/TCP and Sony SRG-300H over Sony-framed UDP. Compatibility depends on exact camera model, firmware and profile.

Start with a test setup and back up existing settings. Preset Set and Profiler command tests can move the camera or overwrite camera presets. Configure camera video separately in OBS.

## Feedback

Please use CAMERA-FEEDBACK.md in the download. Include your OS/CPU, OBS version, exact camera model and firmware, selected profile and individual function results. Success reports and new profile JSON files with test evidence are welcome. For problems, include repeatable steps, the exported Profiler trace and the OBS log from the affected session; include the crash report for a crash. Remove private information before posting. Reply in the OBS forum discussion where you obtained the download or use this repository’s Issues tab.

## Roadmap

The goal is to refine SimpleCamPTZ through community feedback, then make the source repository public with version 1.0. This repository hosts downloads and documentation only; the plugin source remains private. GitHub’s automatic Source code ZIP/tar archives contain this download repository’s README, not the plugin source or installers.
