# Changelog

**v3.5.0**

For Hotrod version `3.5.0`.

- The variable `hotrod_server_enable_server_agent`, if set, must be set to `true`
- New variable: `hotrod_agent_api_bind_address` with default `127.0.0.1:4041`
- New variable: `hotrod_server_agent_bind_address` with default `127.0.0.1:3041`
- Example `test_cluster_install.yml` now has 1 agent, instead of 2, since the server agent is no longer optional, and default license only allows for 2 agents

**v0.9.0**

For Hotrod version `3.4.x`.

- Initial release, supporting Hotrod >= 3.1.2, and targeting Ubuntu 18.04 and 20.04