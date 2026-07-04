# Roadmap

`ansible-role-secure_user` is a small, single-purpose Ansible role and is
**stable** (published to Ansible Galaxy at `v1.0.2`). It does one job — provision
a sudo-enabled user with key-based SSH auth and password logins disabled — and
does it well. It is maintained, not actively expanded.

## Maintenance

- Keep the role working against current Ubuntu LTS releases and Ansible versions.
- Address any bugs or security issues promptly and cut a patch release.

## Nice-to-haves

These are genuine, self-contained improvements — none are committed or urgent.

- [ ] Add Molecule + CI test coverage so the role is exercised against a real
      container on every PR, rather than lint-only.
- [ ] Make the copied public key configurable (accept a `user_ssh_key` variable)
      instead of always sourcing from `/root/.ssh/authorized_keys`.
- [ ] Parameterize hardcoded assumptions (sudo group name, target shell) as role
      variables with sensible defaults, to broaden distro support beyond Ubuntu.
