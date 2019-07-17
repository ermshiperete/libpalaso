# Change Log

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

<!-- Available types of changes:
### Added
### Changed
### Fixed
### Deprecated
### Removed
### Security
-->

## [Unreleased]

### Changed

- Create nuget packages
- [SIL.Media] `IAudioRecorder.SelectedDevice` now returns a `IRecordingDevice` which both the
  NAudio and AlsaAudio `RecordingDevice` implement. This allows to use the same assembly
  on both Windows and Linux (although the limitations what works and what doesn't work remain the
  same)
- [SIL.Media] cleanup of `AudioSession` API: rename `AudioIrrKlangSession` to `WindowsAudioSession`.
  `AudioAlsaSession` and `WindowsAudioSession` are now  internal (they were never intended to
  be used directly)
- [SIL.Media] move some interfaces around so that they live in `SIL.Media` instead of
  `SIL.Media.Naudio`: `IAudioRecorder`, `RecordingState`, `IAudioPlayer`

### Added

- [SIL.Core] new properties for processor architecture: `Platform.ProcessArchitecture` and
  `Platform.IsRunning64Bit`

### Deprecated

- [SIL.Core] Deprecated `SIL.Progress.ProgressState`. Use one of the `SIL.Progress.IProgress`
  classes (e.g. `SIL.Progress.MultiProgress`, `SIL.Progress.ConsoleProgress`,
  `SIL.Progress.StatusProgress`, `SIL.Progress.FileLogProgress`,
  `SIL.Windows.Forms.Progress.TextBoxProgress`) instead, possibly along with
  `SIL.Windows.Forms.Progress.LogBox`.
- [SIL.Core] Deprecated `SIL.Progress.NullProgressState`. Use `SIL.Progress.NullProgress` instead.
- [SIL.Core] Deprecated `SIL.Progress.ConsoleProgressState`. Use `SIL.Progress.ConsoleProgress`
  instead.
- [SIL.Core] Deprecated `SIL.Progress.BackgroundWorkerState`.
- [SIL.Windows.Forms] Deprecated `SIL.Windows.Forms.Progress.ProgressDialogProgressState`.
