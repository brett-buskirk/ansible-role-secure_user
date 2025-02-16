# ansible-role-secure_user

This Ansible role creates a new user account with sudo privileges and sets up key-based SSH authentication.

## Requirements

* An Ubuntu-based system.
* Ansible.
* Root privileges (via `become: true`).
* An SSH key pair for the new user.
* The public key of the key pair should be placed in `/root/.ssh/authorized_keys` on the target host.

## Role Variables

| Variable Name | Description | Default Value |
|---|---|---|
| `user_name` | The username to create. | `None` (required) |

## Dependencies

This role has no dependencies.

## Example Playbook

```yaml
- hosts: your_hosts
  become: true
  vars:
    user_name: brett  # Replace with the desired username
  roles:
    - secure_user
```

## Installation

You can install this role using Ansible Galaxy:

```bash
ansible-galaxy role install brett-buskirk.secure_user
```

Or you can include it in your `requirements.yml` file:

```yaml
---
roles:
  - name: brett-buskirk.secure_user
    src: https://github.com/brett-buskirk/ansible-role-secure_user
```

Then install it using:

```bash
ansible-galaxy install -r requirements.yml
```

## Role Tasks

This role performs the following tasks:

* **Update apt cache:** Updates the apt package cache to ensure the latest package information is available.
* **Create sudo user:** Creates a new user account with the specified username, adds it to the sudo group, sets the default shell to `/bin/bash`, and creates the user's home directory.
* **Create.ssh directory:** Creates the `.ssh` directory in the user's home directory and sets appropriate permissions.
* **Copy root's authorized_keys:** Copies the `authorized_keys` file from the root user's `.ssh` directory to the new user's `.ssh` directory, enabling key-based authentication.
* **Disable password authentication for SSH:** Disables password authentication for SSH to enforce key-based authentication.

## Usage

1. **Define `user_name`:** In your playbook, define the `user_name` variable with the desired username.
2. **Place SSH key:** Ensure the public key of the user's SSH key pair is in `/root/.ssh/authorized_keys` on the target host.
3. **Include the role:** Include the `secure_user` role in your playbook.

## License

MIT

## Author Information

Brett Buskirk
