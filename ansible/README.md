# Ansible system management

In order to configure this for your own cluster, you will need to adjust the
inventory found in `hosts`.  I would recommend using the `[unconfigured]` group
and the `new_hostname` variable in order to assign the appropriate hostnames to
all nodes in your cluster.  You can do so with the `setup-hostnames.yaml`
playbook.

## Auxilary Files

| Filename | Description |
|-|-|
| [**./hosts**](./hosts) | Inventory file I used for this project |
| [**./pastables.txt**](./pastables.txt) | Various useful commands that are used by pasting in a terminal.  This includes some necessary components for first time setup! |

## Playbooks

| Filename | Description |
|-|-|
| [**./setup-hostnames.yaml**](./setup-hostnames.yaml) | Takes unconfigured nodes and assigns a new hostname based on the `new_hostname` variable.  Updates immediately and does not require a reboot |
| [**./setup-ssh.yaml**](./setup-ssh.yaml) | Disables password authentication, future goal is to install ssh keys automatically<sup>*</sup> |
| [**./update-packages.yaml**](./update-packages.yaml) | `sudo apt update; sudo apt upgrade` |
| [**./setup-docker.yaml**](./setup-docker.yaml) | Installs Docker CE for Raspbian Buster |

<sup>*</sup> Running in to a snag here since it would require passphrase
authentication, which is not working out of the box on MacOS

## Known Issues

- Python 2 implementation of `docker` and `docker-py` seems to be broken and
  unusable for Ansible.  Set your Ansible vars to include
  `ansible_python_interpreter=/usr/bin/python3`, which can be seen in
  [**./hosts**](./hosts)