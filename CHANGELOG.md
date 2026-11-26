# Changelog

All notable changes to this project are listed here. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and versions follow
[Semantic Versioning](https://semver.org/).

## [1.0.0] - 2026-11-26

A ROS Melodic and Gazebo simulation of a Neobotix MPO-500 mecanum base with two UR5 arms. It maps, localises and navigates with two lidars, and plans for both arms with MoveIt and IKFast.

### Added

- The original 2020 work is the robot setup built on `neo_simulation`, which began as Neobotix's package. It covers the MPO-500 and two-UR5 model, Gazebo worlds, mapping and navigation configs, `mpo_500_moveit_config` for both arms and one IKFast plugin per arm.
- `dependencies.repos`, which pins `neo_kinematics_mecanum`, `gazebo-pkgs` and `general-message-pkgs` for vcstool.
- `package.xml` dependency lists, a BSD 3-Clause license and a `.gitignore`.
- A README with a system diagram, an interface table, setup, usage, extension points and limitations.

### Changed

- The perception demo's launch files point at `neo_simulation`, where they pointed at `six_dof` before. The map, the camera URDF and the IKFast update scripts no longer point at a home directory.
- The laser merger launch file now lives in `neo_simulation/launch/mpo_500/`.

### Removed

- The vendored copies of `navigation`, `neo_kinematics_mecanum`, `neo_local_planner`, `neo_teleop`, `universal_robot` and `ira_laser_tools`. `dependencies.repos` now pins `neo_kinematics_mecanum`.
- The generated `mpo_500.urdf`. The xacro stays.

[1.0.0]: https://github.com/AdilShaikh1/dual_arm_mobile_manipulator/releases/tag/v1.0.0
