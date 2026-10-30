# Changelog

## [Unreleased]

### Added
- Added explicit `voice_id` support to voice uploads so server-managed cloned voices can be replaced without reusing the display name.
- Added `GET /api/voices/{voice_id}/file` to fetch the uploaded WAV file for a voice.
- Added `DELETE /api/voices/{voice_id}` to remove a voice and clear its cached TTS state.

### Changed
- Voice IDs are normalized consistently when uploaded, including converting underscores to hyphens.
- Uploading a voice now invalidates stale cached voice state so fresh samples are recognized immediately.

### Fixed
- Fixed stale voice cache behavior after replacing or deleting an uploaded custom voice.
