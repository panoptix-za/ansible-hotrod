# Hotrod Ansible Role

This Ansible role installs and configures the Hotrod binary, Hotrod server and Hotrod agents.

See Hotrod's [installation guide](https://hotrod.app/docs/install/overview), and [environment variables](https://hotrod.app/docs/reference/environment_variables).


## Supported Systems

This role supports Ubuntu 18.04 and 20.04.

`./tasks/preflight.yml` will abort the playbook if the target system is not supported.


## Variables

### Control Variables

Four variables control the behaviour of this role:

**`hotrod_download_uri`**  
(Default: none)

The URI of the Hotrod binary release to download, which determines the installed version. See [downloads](https://hotrod.app/docs/install/download) for obtaining this URI.

**`hotrod_download_uri_sha1`**  
(Default: `{{ hotrod_download_uri }}.sha1`)

The URI of the SHA1 checksum associated with `hotrod_download_uri`. No need to change this when performing standard downloads.

**`hotrod_system_group`**  
(default: `hotrod`)

The user group to run Hotrod server/agent as. The group is created if it doesn't exist (unless `root`, but you shouldn't run Hotrod as root).

**`hotrod_system_user`**  
(default: `hotrod`)

The system user to run Hotrod server/agent as. The user is created if it doesn't exist (unless `root`, but you shouldn't run Hotrod as root).

**`hotrod_install_binary`**  
(default: `no`)

If yes, downloads and installs the Hotrod binary on the target system, as specified by `hotrod_download_uri`.

**`hotrod_install_server`**  
(default: `no`)

If yes, installs and configures Hotrod server. Implies `hotrod_install_binary: yes`.

**`hotrod_install_agent`**  
(default: `no`)

If yes, installs and configures Hotrod agent. Implies `hotrod_install_binary: yes`.

### Additional Variables

See [./defaults/main.yml](./defaults/main.yml) for customizing the Hotrod installation. Variables are documented, and most have reasonable defaults.


## Licence

While this Ansible role is made available under the MIT license, note that the use of Hotrod is subject to the Panoptix [End User License Agreement](https://hotrod.app/eula).