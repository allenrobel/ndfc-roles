# ndfc_device_generated_configs_get

Retrieve populated generated configs from ``device_name`` in fabric ``fabric_name``

Store in variable ``device_generated_configs``

### Role Variables

Variable        | Type  | Description
----------------|-------|----------------------------------------
device_name     | str() | The device in ``fabric_name`` to query
fabric_name     | str() | The fabric in which ``device_name`` resides

Fabric and device parameters are defined in the following file:

``./roles/ndfc_common/vars/main.yml``

See the following for details:

[./roles/ndfc_common/README.md](https://github.com/allenrobel/ndfc-roles/tree/master/roles/ndfc_common/README.md)


### Example Playbook

```yaml
---
- hosts: ndfc
  gather_facts: false
  roles:
    - ndfc_device_generated_configs_get
  vars:
    fabric_name: f1
    device_name: leaf_1
  tasks:
  - block:
    - debug:
        var: device_generated_configs
    when: "device_generated_configs != ''"
```

### Licensing

GNU General Public License v3.0 or later.

See [LICENSE](https://www.gnu.org/licenses/gpl-3.0.txt) for full text.

### Author Information

Allen Robel (@packetcalc)