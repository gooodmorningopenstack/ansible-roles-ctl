# Ansible roles management

The goal of this tool is to manage installation and upgrade of Ansible
roles using git versions (tags and branches).

Currently this tool is EXPERIMENTAL.

This tool uses the `requirements.yml` configuration file used by Ansible
Galaxy. The syntax is unchanged and the ansible-galaxy tool can be used
by people not involved in playbooks development.

Roles managed manually, bare, or in a bad shape are ignored (with proper
warning).

Follows documentation about the various subcommands.

## Status

    ansible-roles-ctl status

This subcommand display a status report about all required external
roles.
