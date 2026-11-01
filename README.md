# SimpleCamPTZ community testing downloads

SimpleCamPTZ is a native OBS plugin for manual PTZ camera control and scene-triggered preset recall, with a dockable or floating control window.

## Download

Open [Releases](https://github.com/wzaggle/SimpleCamPTZ-Releases/releases) and select **v0.2.0 — Community Testing Pre-release**. Download the installer ZIP under Assets. The illustrated User Guide PDF is also available separately.

Packages are provided for Windows x64, Intel Mac, Apple Silicon Mac and Ubuntu 24.04 with native OBS. The ZIP includes installation instructions, a quickstart, release notes, Camera Profiler guide and camera feedback template. Mac packages are ad-hoc signed and not notarized; Ubuntu packages do not target Flatpak or Snap OBS.

## Community testing pre-release

Version 0.2.0 is intended for interested users who want to help refine the plugin, identify problems and expand the collection of camera profiles through real hardware testing. Bundled profiles cover AViPAS AV-1280W over raw VISCA/TCP and Sony SRG-300H over Sony-framed UDP. Compatibility depends on the exact camera, firmware and profile.

All four native builds passed automated test suites, and the maintainer reports installation and camera operation on all four platforms. Broader testing continues. Start with a test setup and back up existing settings. Preset Set and Profiler command tests can move the camera or overwrite camera presets. Configure camera video separately in OBS.

## Feedback

Please use CAMERA-FEEDBACK.md in the download. Include your OS, OBS version, exact camera model, selected profile and individual function results. Success reports and new profile JSON files with test evidence are welcome. For problems, include repeatable steps and the OBS log from the affected session; include the crash report for a crash. Remove private information before posting. Reply in the OBS forum discussion where you obtained the download or use this repository’s Issues tab.

## Roadmap

The goal is to refine SimpleCamPTZ through community feedback, then make the source repository public with version 1.0. This repository hosts downloads and documentation only; it contains no plugin source code.
