# Ansible Role - My Couchpotato Server

A role for managing a
[Couchpotato](https://github.com/CouchPotato/CouchPotatoServer) installation.

## Requirements

None.

## Role Variables

- `couchpotato_systemd_supplementary_groups` - a list of groups keyed to the
  CouchPotato systemd unit's `SupplementaryGroups`.  Default is
  `['downloads']`.
- `couchpotato_settings` - a hash of settings to merge into CouchPotato's
  configuration file.  By default the hash is empty.
- `couchpotato_data_dir` - directory where Couchpotato should store its
  database, cache, and other data sources.  Defaults to
  `/var/data/couchpotato`.
- `couchpotato_config_file` - Couchpotato's configuration file.  Defaults to
  `{{ couchpotato_data_dir }}/config.ini`.

## Example Playbook

```yaml
- hosts: couchpotato
  roles:
    - role: BaxterStockman.couchpotato
      couchpotato_data_dir: '/opt/couchpotato'
      couchpotato_config_file: '/etc/couchpotato.ini'
      couchpotato_settings:
        core:
          port: 8111
        manage:
          library: /my/media/library
```

## License

MIT

## Author Information

Matt Schreiber <mschreiber@gmail.com>
