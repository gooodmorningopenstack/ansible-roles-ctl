# Ansible roles management

The goal of this tool is to manage installation and upgrade of Ansible
roles using git tags and branches.

This tool uses the `requirements.yml` configuration file used by Ansible
Galaxy. The syntax is unchanged and the ansible-galaxy tool can be used
by people not involved in playbooks development.

This tool assumes a **role version** follows [semantic versioning](http://semver.org/spec/v2.0.0.html)
and is labelled with a git tag of the form _vX.Y_ or _vX.Y.Z_ (examples: v1.0 or v2.3.1).

Roles managed manually, bare, or in a bad shape are ignored (with proper
warning).

Syntax is as follow:

    ansible-roles-ctl [global options] [subcommand] [subcommand options]

You can use -h/--help option to list all available options at command
and subcommand level, as well as all available subcommands.

Follows documentation about the various subcommands.

## Status

    ansible-roles-ctl status

This subcommand display a status report about all required roles.

You can limit output to a selection of roles:

    ansible-roles-ctl status mailman3 httpd

The -c/--changelog option displays changelog entries if available.

## Install

    ansible-roles-ctl install

This subcommand install all roles listed in the requirements.

You can limit this action to a selection of roles:

    ansible-roles-ctl install bind9 postfix

## Update

    ansible-roles-ctl update

This subcommand update all roles listed in the requirements to the
latest version.

You can limit this action to a selection of roles:

    ansible-roles-ctl update bind9 postfix

It is possible to update roles to a particular version and update the
requirements (downgrade is possible):

    ansible-roles-ctl update bind9=1.1

**WARNING**: at the moment the requirements file is not yet updated by
this script.

