# OpenBSD Ansible Playbook

Ansible playbook for provisioning and configuring OpenBSD nodes.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Note](#note)
- [Author](#author)
- [License](#license)

## Prerequisites
- Ansible installed
- SSH access to an OpenBSD node

## Usage
0. Clone the repository and change into its directory:
```bash
git clone https://github.com/ggragham/openbsd_ansible.git && cd openbsd_ansible/
```
1. Copy the inventory file template (`inventory.ini.template`) to `inventory.ini` and adjust it for your OpenBSD node.
2. Use `default.vars.yml` and `default.playbook.yml` as templates for your configuration. Rename them as needed (e.g., `openbsd.vars.yml`/`openbsd.playbook.yml`). These files will be excluded from Git (see [`.gitignore`](./.gitignore)).
3. Copy/rename `default.pf.conf.j2` from `./assets`, adjust it for your ruleset, and set its path in `*.vars.yml`. Files in `./assets` are excluded from Git too (see [`.gitignore`](./.gitignore)).
4. Run your chosen playbook using:
```bash
ansible-playbook openbsd.playbook.yml
```
You can also use the `--tags=""` and/or `--skip-tags=""` options to include or exclude tasks. For example:
```bash
ansible-playbook openbsd.playbook.yml --tags="network,ssh,pkgs" --skip-tags="update"
```

## Note
This was made for personal use and learning. Feel free to use it as a template for your own setup.

## Author
This project was created by [Grell Gragham](https://github.com/ggragham).

## License
This software is published under the DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE license.

