# Ansible system management

In order to configure this for your own cluster, you will need to adjust the
inventory found in `hosts`.  I would recommend using the `[unconfigured]` group
and the `new_hostname` variable in order to assign the appropriate hostnames to
all nodes in your cluster.  You can do so with the `setup-hostnames.yaml`
playbook.

## Playbooks

| Filename | Description |
|-|-|
| [**./hosts**](./hosts) | Inventory file I used for this project |
| [**./setup-hostnames.yaml**](./setup-hostnames.yaml) | Takes unconfigured nodes and assigns a new hostname based on the `new_hostname` variable.  Updates immediately and does not require a reboot |
| [**./setup-ssh.yaml**](./setup-ssh.yaml) | Disables password authentication, future goal is to install ssh keys automatically<sup>*</sup> |
| [**./update-packages.yaml**](./update-packages.yaml) | `sudo apt update; sudo apt upgrade` |
| [**./setup-docker.yaml**](./setup-docker.yaml) | Installs Docker CE for Raspbian Buster |
<sup>*</sup> Running in to a snag here since it would require passphrase
authentication, which is not working out of the box on MacOS