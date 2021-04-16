# BetterDiscord Changelog

This changelog starts with the restructured 1.0.0 release that happened after context isolation changes. The changelogs here should more-or-less mirror the ones that get shown in the client but probably with less formatting and pizzazz.

## Unreleased

### Added
- Added an option to prevent Discord from hijacking the media keys.
- Added command line flag to launch a vanilla version of Discord `--vanilla`
- Added an option for app-wide `ctrl+shift+c` shortcut for inspect element.
- Added emote blocklist to `BdApi` via `BdApi.Emotes.blocklist`.
- Added the ability to remove Discord's forced minimum window size.
- Added a basic core updater to hopefully prevent the need for future installs.
- Added an option to log out all console logs to file for developers.
- Added an option to disable Discord's console warning.

### Removed
- Class normalizer was removed as it does more harm than good.

### Changed
- Addon error modals got a makeover thanks to [Strencher](https://github.com/Strencher) and [Tropical](https://github.com/Tropix126)
- Emotes are now downloaded as a single asar bundle as opposed to individual JSON files.
- Strings are now bundles with the main payload, but may move to a separate asar like the emotes.
- `BdApi` functions related to window preferences no longer work and are deprecated.
- Guild classes are obtained later from webpack in case it's not loaded in fast enough.
- DataStore now has additional protections (`try..catch`).

### Fixed
- Fixed an issue with old METAs used in themes cause the css to render invalid.
- Fixed crashing issues with plugins using `Buffer`.
- Fixed a bug for manual and 3rd party installations that don't create the BD folder.
- Fixed incorrect path usage for some Mac devices.
- Fixed colored text not doing anything.
- Fixed detached css window not loading saved css.
- Fixed an issue where toggling settings collections would remove incorrect panels.
- Fixed the file watchers not properly matching duplicate files.
- Fixed Hide GIF and Hide Gift options for Discord's changes
- Fixed public servers button not showing.
- Fixed multiple error modals showing on startup if multiple plugins had errors.
- Fixed incorrect styling on emotes.
- Fixed system editor edit buttons using an old Electron API (`openItem` vs `openPath`)


## 1.0.0

### Added
- **Everything** is entirely rewritten, for better or worse.
- **Emotes and Custom CSS** can be completely turned off for those not interested. It saves on memory too by not loading those components.
- **Floating editors** for both custom css and plugins/themes are now available.
- **Monaco** is now used as the main CSS editor, in place of Ace.
- **Settings panels** are completely new and sleek. They are also highly extensible for potential future features :eyes:
- **Translations** are now integrated starting with only a couple languages, but feel free to contribute your own!
- **Public servers** got a new makeover thanks to some design help from Tropical and Gibbu!
We added settings to hide the **Gif Picker** and the **Nitro Gift** buttons in the textarea.

### Changed
- **Patcher API** was added to `BdApi` under `BdApi.Patcher`. The old `BdApi.monkeyPatch` was patched to use the Patcher as well. This allows plugins and patches to play nice with one another.
- **jQuery** was removed from dependencies.
- **General performance** improvements throughout the app, from startup to emotes to addons.
- **Exporting** by plugins is now highly encouraged over trying to match your meta name and class name.
- **Plugins and Themes** pages have more options for sorting, views and more. The entire panel got a facelift!
- **Blankslates** have been added all over for that added UX.
- **Several unused UI features** have been removed for a more performant and usable experience.
- **Debugger Hotkey** is now a built-in feature!

### Fixed
- **Minimal mode** has been redesigned from the ground up and now works as intended.
- **Emote menus** are fixed and now use React Patching to properly integrate into the new Emoji Picker. (Thanks Strencher#1044!)