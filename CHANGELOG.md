# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [Unreleased][unreleased]

### Added

- New tests for overspeed fault behavior
- New tests for fan speed behavior
- Testing with Tox to ensure compatibility with all supported Python versions
- Support for new firmware verbs:
  - CLEAR_SYSTEM_FAULT (232)
  - SET_OVERSPEED_ENCODER_THRESHOLD_ENCODER_100HZ (16)
  - SET_OVERSPEED_DURATION_100MS (17)
  - SET_BRAKE_ON_FAULT (18)
- Support for new firmware data elements:
  - FAN1_DUTY (78)
  - FAN2_DUTY (80)
  - SYSTEM_FAULT_FLAGS (82): (overspeed / overcurrent)

### Fixed

- Serial error handling could previously throw a TypeError on failure to connect to a device instead of an OpenRoverException
- No more warning when running on Ubuntu: "RuntimeWarning: You seem to already have a custom sys.excepthook handler installed."

### Changed

- More docs.
- Dropped support for Python3.5
- (dev) This project now builds with `poetry` instead of `setuptools` to provide simpler release process.
- (dev) Code formatting is now done with Black.

## [0.3.1][0.3.1] - 2019-05-08

### Added

- Add new configuration options for speed in hHz and speed limit
  percent.
- Support for new firmware verbs:
  - SET_PWM_FREQUENCY_100HZ (14)
  - SET_SPEED_LIMIT_PERCENT (15)

### Fixed

- Fix improper reporting of version number for legacy firmware.

## [0.2.1][0.2.1] - 2019-04-22

### Added

- Python 3.5 compatibility.

- Add pitstop, a command line utility to bootload and configure the rover.

- Add license, package for PyPI

- Many new tests

- Support for firmware data elements 0,2,...76

- Support for firmware verbs:
  - NOP (0)
  - GET_DATA (10)
  - SET_FAN_SPEED (20)
  - RESTART (230)
  - SET_DRIVE_MODE (240)
  - FLIPPER_CALIBRATE (250)
  - RELOAD_SETTINGS (1)
  - COMMIT_SETTINGS (2)
  - SET_POWER_POLLING_INTERVAL_MS (3)
  - SET_OVERCURRENT_THRESHOLD_100MA (4)
  - SET_OVERCURRENT_TRIGGER_DURATION_5MS (5)
  - SET_OVERCURRENT_RECOVERY_THRESHOLD_100MA (6)
  - SET_OVERCURRENT_RECOVERY_DURATION_5MS (7)
  - SET_PWM_FREQUENCY_KHZ (8)
  - SET_BRAKE_ON_ZERO_SPEED_COMMAND (9)
  - SET_BRAKE_ON_DRIVE_TIMEOUT (11)
  - SET_MOTOR_SLOW_DECAY_MODE (12)
  - SET_TIME_TO_FULL_SPEED (13)

### Changed

- Changed license from BSD 2-clause to 3-clause
- Update TIME_TO_FULL_SPEED to make it in deciseconds.
- Use Trio for async

### Fixed

- Fix requirement for setuptools_scm (should be setuptools-scm)
- Fixed issue which made protocol test fail

## 0.0 (2018-11-14)

### Added

- Basic Python Driver functionality

[unreleased]: https://github.com/olivierlacan/keep-a-changelog/compare/0.3.1...HEAD
[0.3.1]: https://github.com/RoverRobotics/openrover-python/compare/0.2.1...0.3.1
[0.2.1]: https://github.com/RoverRobotics/openrover-python/compare/0.0...0.2.1