[![Galaxy](http://img.shields.io/badge/galaxy-cchurch.unifi--camera--logo-blue.svg)](https://galaxy.ansible.com/cchurch/unifi-camera-logo/)

Unifi Camera Logo
=================

Configure custom logo on Unifi Protect cameras.

Requirements
------------

The Unifi camera(s) must have SSH enabled and be accessible via Ansible.

Role Variables
--------------

The following variables may be defined to customize this role:

- `unifi_camera_logo_use_custom`: Boolean indicating whether to use a custom
  logo; default is `true`. Set to `false` to restore the default logo.
- `unifi_camera_logo_file`: Filename/path to a custom logo file; default is
  `"unifi_camera_logo.png"`. Recommended to be an 8-bit grayscale PNG.
- `unifi_camera_logo_scale`: Integer value between 1 and 100 indicating the
  the scale of the logo overlay in the lower right corner; default is `50`.

Dependencies
------------

None.

Example Playbook
----------------

The following playbook updates admin users on dev and prod servers with
different options:

    - name: Configure custom logo and scale
      hosts: unifi_cameras
      gather_facts: false
      roles:
        - role: cchurch.unifi_camera_logo
          unifi_camera_logo_file: my_custom_logo.png
          unifi_camera_logo_scale: 100

License
-------

BSD

Author Information
------------------

Chris Church ([cchurch](https://github.com/cchurch))
