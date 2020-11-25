# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
- forked from MSDRobotics/roboclaw_ros
    - thread safe with mutex
    - odom fix
    - maybe something more...
- tested with firmware 4.1.34

### Added
- added gitignore file with ROS template

### Changed
- updated roboclaw_driver from most recent [roboclaw_python_library](https://github.com/basicmicro/roboclaw_python_library)
- updated status/error bit mask according to User Manual Revision 5.7 for Firmware 4.1.34 and Newer
- changed verbosity

### Removed
- removed python byte-code files
