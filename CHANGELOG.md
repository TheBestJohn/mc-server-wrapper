# mc-server-wrapper changelog

Notable `mc-server-wrapper` changes, tracked in the [keep a changelog](https://keepachangelog.com/en/1.0.0/) format with the addition of the `Internal` change type.

## [Unreleased]

### Internal

* Replace `tui` with `ratatui` 0.21.0

## [alpha8] - 2023-06-08

Dependency updates and adjustments for the new Discord username format.

## Added

* `--version` flag for checking the application version

### Changed

* Chat message formatting has been updated to handle the new Discord username system.

### Internal

* Updated `twilight` to 0.15
* Updated `tui` to 0.19
* Updated `crossterm` to 0.26.0
* Updated `toml` to 0.7
* Replaced `notify` with `notify-debouncer-mini` 0.3.0
* Updated `textwrap` to 0.16.0
* Updated other dependencies
* Renamed `master` branch to `main`
* Added RELEASE.md documenting how to release `mc-server-wrapper`

## [alpha7] - 2022-3-21

Small release updating some dependencies.

### Changed

* All commands in Discord chat have been removed (aka `!mc list`). These commands need to be brought back in the future as interactions, a new Discord API feature
* Removed all usage of the `chrono` crate and replaced it with the `time` crate for datetime operations

### Internal

* Added dependency on `time` 0.3
* Updated `twilight` to 0.10
* Updated `tui` to 0.17
* Updated `crostterm` to 0.23.1
* Updated `textwrap` to 0.15
* Removed dependency on `chrono`
* Updated other dependencies

## [alpha6] - 2021-11-17

Small release updating some dependencies.

### Changed

* The hover text for embed links in Minecraft now includes the full link URL

### Internal

* Updated `twilight` to 0.7
* Updated `crossterm` to 0.22
* Updated `tui` to 0.16
* Updated `textwrap` to 0.14
* Updated `tokio` to 1.8.1
* Updated other dependencies
* Removed `rusty-hook` and its corresponding git hooks

## [alpha5] - 2021-5-24

Small release updating some dependencies.

### Internal

* Updated `tokio` to 1.0
* Updated `twilight` to 0.4
* Updated `tui` to 0.15
* Updated other dependencies
* Replaced `minecraft-protocol` dependency with `minecraft-chat`

## [alpha4] - 2020-12-20

### Added

* Mentions within Discord are now formatted with a blue color in Minecraft (similar to how they look in the Discord client)
* Hovering over the username part of a Discord message in Minecraft will now reveal the Discord user's account name and discriminator (e.g. Cldfire#3395)
  * Also displayed when hovering over user mentions
  * This information is now logged as well

### Changed

* `Tab` / `Shift + Tab` are now the shortcuts used to change tabs in the UI

### Fixed

* The session times displayed in the "Players" tab are now accurate

### Internal

* Removed dependency on `ringbuffer` (using `VecDeque` instead)

## [alpha3] - 2020-12-15

### Added

* The UI now has a "Players" tab to display information about players on the server
  * Displays a list of online players with login time and session length

### Changed

* We no longer attempt to fetch missing member info via Discord's HTTP API if it is not present in the cache ([explanation](https://github.com/twilight-rs/twilight/pull/437))
  * This should not have any user-facing impact because technically speaking all needed info will be present in the cache anyway
* The config that gets generated by default now includes a blank `[discord]` section for easier Discord bridge setup

### Fixed

* Minecraft player names are no longer markdown-sanitized for display in the bot status (the bot status message doesn't support markdown)

### Internal

* Updated to `twilight` 0.2 release from crates.io
* Replaced custom mention parsing code with the new `twilight-mention` support for parsing mentions from Discord messages
* Started adjusting the binary's `Cargo.toml` version for each release
* Added a deps.rs badge to the README
* Updated workflows
  * Clippy job now denies warnings
  * Daily audit job is now a weekly audit job

## [alpha2] - 2020-08-22

### Added

* The bot's status message is now updated with server information (such as the names of online players)
* Content that failed to validate will now be logged alongside the warning that a message failed to send to Discord

## [alpha1] - 2020-07-26

Tagging a first alpha release after a few months of working on the project.

[Unreleased]: https://github.com/Cldfire/mc-server-wrapper/compare/alpha8...HEAD
[alpha8]: https://github.com/Cldfire/mc-server-wrapper/compare/alpha7...alpha8
[alpha7]: https://github.com/Cldfire/mc-server-wrapper/compare/alpha6...alpha7
[alpha6]: https://github.com/Cldfire/mc-server-wrapper/compare/alpha5...alpha6
[alpha5]: https://github.com/Cldfire/mc-server-wrapper/compare/alpha4...alpha5
[alpha4]: https://github.com/Cldfire/mc-server-wrapper/compare/alpha3...alpha4
[alpha3]: https://github.com/Cldfire/mc-server-wrapper/compare/alpha2...alpha3
[alpha2]: https://github.com/Cldfire/mc-server-wrapper/compare/alpha1...alpha2
[alpha1]: https://github.com/Cldfire/mc-server-wrapper/releases/tag/alpha1
