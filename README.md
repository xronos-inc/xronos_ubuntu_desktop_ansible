# Ansible role for installing Ubuntu Desktop

This role installs Ubuntu Desktop with configuration amenable to use with GPU-enabled cloud instances.

Features:

- installs Ubuntu Desktop
- disables Wayland protocol (needed by NICE-DCV)
- installs Firefox (optional)
- installs desktop background (optional)

## Requirements

Provisioning host:

- ansible 2.15 or later

Host that will run docker

- Ubuntu 22.04 or later (or equivalent Debian-based distro running apt)

## How to use this role

Add this role to your Ansible playbook file.

```yaml
- name: install ubuntu desktop
  role: xronos_ubuntu_desktop_ansible
```

## Variables

- `ubuntu_desktop_configure_wallpaper` (= `true`): configure Xronos wallpaper and lock screen.
- `ubuntu_desktop_install_firefox` (= `true`): install Firefox.
