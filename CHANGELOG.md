# Changelog

All notable changes to ansible-role-secure_user are documented here. The format is based on
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.2] - 2025-02-16

### Changed
- Documentation-only release. Clarified the `requirements.yml` installation
  example in the README to pull the role explicitly from Ansible Galaxy. Role
  behavior is unchanged from 1.0.0.

## [1.0.0] - 2025-02-16

### Added
- Initial release of the `secure_user` Ansible role.
- Creates a new user account with the specified `user_name` and adds it to the
  `sudo` group, sets the login shell to `/bin/bash`, and creates the home
  directory.
- Sets up key-based SSH authentication by creating the user's `.ssh` directory
  (mode `0700`) and copying `authorized_keys` from root (mode `0600`).
- Disables SSH password authentication (`PasswordAuthentication no`) and
  restarts the SSH service via handler to enforce key-based logins.
- Galaxy metadata (`meta/main.yml`) targeting Ubuntu, `min_ansible_version: 2.9`.

[Unreleased]: https://github.com/brett-buskirk/ansible-role-secure_user/compare/v1.0.2...HEAD
[1.0.2]: https://github.com/brett-buskirk/ansible-role-secure_user/compare/v1.0.0...v1.0.2
[1.0.0]: https://github.com/brett-buskirk/ansible-role-secure_user/releases/tag/v1.0.0
