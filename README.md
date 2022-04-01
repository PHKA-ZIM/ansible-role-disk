# Disk setup automation with ansible

## Installation steps

- Go to you ansible project folder
- Add following to your requirements file

```
- src: https://github.com/PHKA-ZIM/ansible-role-disk
  name: ansible-role-disk
```

- Install to project roles path
```
ansible-galaxy install -r requirements.yml --roles-path ./roles
```

## Use ansible-role-disk

- Import role and override role variables, e.g.
```
- name: Setup disk
  roles:
    - role: ansible-role-disk
      vars:
        disk_device: /dev/sdb
        disk_number: 1
        disk_fs_type: btrfs
        disk_part_start: 0%
        disk_part_end: 100%
        disk_mount_path: /var/www-data-part
```
