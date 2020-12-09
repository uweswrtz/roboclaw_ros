# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
- forked from [MSDRobotics/roboclaw_ros]
    - thread safe with mutex
    - odom fix
    - maybe something more...
- tested with firmware 4.1.34

### Added
- CHANGELOG
- gitignore file with ROS template
- diagnostics for currents
- main battery voltage publisher (BatteryState)
- option to run without encoders
    - uses duty cycle ( MIXEDDUTY/34 )
    - parameter TICKS_PER_METER is used as duty cycle factor: velocity * TICKS_PER_METER 

### Fixed 
- fixed decimal output of battery and temp diagnostics

### Changed
- updated roboclaw_driver from most recent [roboclaw_python_library](https://github.com/basicmicro/roboclaw_python_library)
- updated status/error bit mask according to User Manual Revision 5.7 for Firmware 4.1.34 and Newer
- changed verbosity
- updated launch to respawn
- updated package.xml with all depends and format 2

### Removed
- removed python byte-code files
