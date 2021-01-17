# Dev Server

This is an Ansible playbook, which sets up my development environment. 

I use VSCode Remote over SSH to this server, so this isn't a collection of clever configuration files and environment tweaks; it's mainly to install the packages I need.

This is intended to be run on an Ubuntu 20.04 install, right after installation. It might work on other distributions but it's probably not wise.

## Assumptions

- The Ubuntu installer created a user, called `jonathan` (replace in the playbook for a different username)
- The Ubuntu installer added `jonathan` to `sudoers`.
- The Ubuntu installer added an SSH key for the user `jonathan`.

The installer will do all of these actions by default.

## Setup

First, install Ansible.

    $ python3 -m venv env/
    $ ./env/bin/pip install ansible

## Running

Run the playbook, specifying the IP of hostname of the server manually (note the trailing comma).

    $ ./env/bin/ansible-playbook --ask-become-pass -i XX.XX.XX.XX, playbook.yml
    BECOME password: <insert-sudo-password-here>
