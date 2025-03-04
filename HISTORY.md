# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.1.2] - 2023-09-18

### Added

- `onAfterInteractive`, `onBeforeInteractive`, `onUnsupported` callbacks

### Changed

- `onVerify` is no longer required

### Removed

- Custom `retry` logic (issue fixed upstream in Turnstile itself)

### Fixed

- Remount issue with certain callbacks (#15)

## [1.1.1] - 2023-06-25

### Added

- `useTurnstile` hook
- `fixedSize` option to reduce layout shift
- Missing argument for `onExpire`
- `BoundTurnstileObject` argument to callbacks

### Fixed

- `global` -> `globalNamespace` (name conflict) (#10)
- Implement `retry` logic ourselves (#14)
- Missing `onError` error argument passthrough

## [1.1.0] - 2023-03-09

### Added

- `refreshExpired` option
- `language` option
- `appearance` option
- `execution` option

### Changed

- Temporary load callback function is now removed after load

### Fixed

- `onTimeout` callback not properly registering
- `ref` not passing properly - pass `userRef` instead
- `globalThis` errors on older browsers

### Removed

- `autoResetOnExpire` - use `refreshExpired` instead

## [1.0.6] - 2022-11-25

### Added

- Support for the new `onTimeout` callback
- `autoResetOnExpire` for automatically resetting the Turnstile widget once the token expires
- `retry` & `retryInterval`
- custom `ref` argument for using your own ref (#7)

## [1.0.5] - 2022-10-22

### Added

- require module support (#6)
- `size` support

## [1.0.4] - 2022-10-11

### Changed

- `onLoad` callback now includes the turnstile widget id (#5)

## [1.0.3] - 2022-10-05

### Fixed

- Race condition by using `useRef` instead of `createRef` (#4)

## [1.0.2] - 2022-10-05

### Added

- Experimental (undocumented) fields `responseField` and `responseFieldName` for controlling the `<input />` element generated by Turnstile.
- `style` prop which is directly passed to the internal `<div />`

### Changes

- Using explicit rendering for Turnstile now which prevents [implicit renders](https://developers.cloudflare.com/turnstile/get-started/client-side-rendering/#implicitly-render-the-turnstile-widget) (also undocumented)
- Using `turnstile.remove()` to remove widgets after being unloaded

### Fixed

- A race condition when loading Turnstile on page load in dev mode has been fixed
- Callback props will now update as expected
- Entrypoint pointing to the wrong file (#3)

## [1.0.1] - 2022-10-01

### Fixed

- Fix double render in vite (#1)
- Fix tslib being a dependency (#2)

## [1.0.0] - 2022-09-29

Initial release.

[unreleased]: https://github.com/Le0Developer/react-turnstile/compare/v1.1.2...HEAD
[1.1.2]: https://github.com/le0developer/react-turnstile/compare/v1.1.1...v1.1.2
[1.1.1]: https://github.com/le0developer/react-turnstile/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/le0developer/react-turnstile/compare/v1.0.6...v1.1.0
[1.0.6]: https://github.com/le0developer/react-turnstile/compare/v1.0.5...v1.0.6
[1.0.5]: https://github.com/le0developer/react-turnstile/compare/v1.0.4...v1.0.5
[1.0.4]: https://github.com/le0developer/react-turnstile/compare/v1.0.3...v1.0.4
[1.0.3]: https://github.com/le0developer/react-turnstile/compare/v1.0.2...v1.0.3
[1.0.2]: https://github.com/le0developer/react-turnstile/compare/v1.0.1...v1.0.2
[1.0.1]: https://github.com/le0developer/react-turnstile/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/Le0Developer/react-turnstile/releases/tag/v1.0.0
