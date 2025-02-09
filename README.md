# Ansible role for installing Ubuntu Desktop

This role installs Ubuntu Desktop with configuration amenable to use with GPU-enabled cloud instances.

Features:

- install Ubuntu Desktop
- install OpenGL
- disable Wayland protocol (needed by NICE-DCV)
- install x11-video-dummy
- install Xronos desktop background 

## Requirements

Provisioning host:

- ansible 2.15 or later

Remote hose:

- Ubuntu 22.04 or 24.04

## How to use this role

Add this role to your Ansible playbook file.

```yaml
- name: install ubuntu desktop
  role: xronos_ubuntu_desktop_ansible
```

## Variables

### Version

- `ubuntu_desktop_version`: Version number of the `ubuntu-desktop` package to install. Default is empty (latest).
- `ubuntu_desktop_reinstall`: Always verify the complete desktop metapackage is installed. Set to `false` to install the metapackage only once, preventing reinstallation of the metapackage if any of its dependencies have been removed. Default is `true`, ensuring the complete metepackage is installed each time this task is run.

### Window Manager

- `ubuntu_desktop_disable_wayland`: Disable Wayland. Default is `false`.
- `ubuntu_desktop_configure_x11_opengl`: Install and configure OpenGL. Default is `true`.
- `ubuntu_desktop_configure_x11_dummy`: Install and configure x11 video dummy. Default is `false`.

### User Experience

- `ubuntu_desktop_configure_wallpaper`: configure Xronos wallpaper and lock screen. Default is `true`.
- `ubuntu_disable_gnome_initial_setup`: disable Gnome initial setup dialog. Default is `true`.
