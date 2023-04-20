[![CI](https://github.com/kmezynski/ansible-role-ohmyzsh/actions/workflows/ci.yml/badge.svg?branch=master)](https://github.com/kmezynski/ansible-role-ohmyzsh/actions/workflows/ci.yml)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/kmezynski/ansible-role-ohmyzsh/master.svg)](https://results.pre-commit.ci/latest/github/kmezynski/ansible-role-ohmyzsh/master)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](LICENSE)
[![Code of Conduct](https://img.shields.io/badge/code%20of%20conduct-Ansible-silver.svg)](.github/CODE_OF_CONDUCT.md)
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-%23FE5196?logo=conventionalcommits&logoColor=white)](https://conventionalcommits.org)

# Ansible Role: Oh My Zsh

Installs and configures [Oh My Zsh](https://ohmyz.sh) with given plugins and
theme on RHEL or Debian/Ubuntu servers.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (refer to
[defaults](defaults) and [vars](vars) directories).

```yaml
ohmyzsh_path: "{{ ansible_user_dir }}/.oh-my-zsh"
ohmyzsh_config_path: "{{ ansible_user_dir }}"
```

These variables control Oh My Zsh installation process:

- `ohmyzsh_path` - path to Oh My Zsh installation directory.
- `ohmyzsh_config_path` - path to Zsh shell initialization script.

```yaml
ohmyzsh_autoupdate: false
ohmyzsh_autoupdate_frequency: 14
ohmyzsh_theme: robbyrussell
ohmyzsh_plugins:
  - git
```

Above variables configures Oh My Zsh after installation:

- `ohmyzsh_autoupdate` - enables Oh My Zsh auto-updates.
- `ohmyzsh_autoupdate_frequency` - auto-updates frequency for Oh My Zsh in days.
- `ohmyzsh_theme` - name of official Oh My Zsh theme.
- `ohmyzsh_plugins` - list of official Oh My Zsh plugins.

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: kmezynski.ohmyzsh
      ohmyzsh_path: "{{ ansible_user_dir }}/.config/zsh/.oh-my-zsh"
      ohmyzsh_config_path: "{{ ansible_user_dir }}/.config/zsh"
      ohmyzsh_autoupdate: true
      ohmyzsh_autoupdate_frequency: 30
```

## License

This role is distributed under the terms of [MIT](https://opensource.org/license/mit/)
license.

## Author Information

This role was created in 2023 by [Kamil Mężyński](https://github.com/kmezynski).
