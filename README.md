# Ansible Role: Swap

Configure swapfile.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    swap_path: "/swapfile"

A swapfile location.

    swap_dd_bs: 256

Block size. Used by `dd`. Hosts with low RAM may need using smaller block size.

    swap_dd_count: 16

Number of blocks. Used by `dd`. Total size (M) of the swapfile equals `swap_dd_bs * swap_dd_count`.

    swap_swappiness: 30

Tendency to use swap, 0 = prevent OOM only, 100 = swap often. Default Ubuntu value is `60`. Read more about [swapiness](https://askubuntu.com/a/103916).

    swap_vfs_cache_pressure: 50

Tendency of the kernel to reclaim the memory which is used for caching of VFS caches, versus pagecache and swap. Increasing this value increases the rate at which VFS caches are reclaimed.

A list of users who will be added to passwordless sudo group.

## Dependencies

None.

## Example Playbook

    - hosts: servers
      roles:
         - { role: danylevskyi.swap }

## TODO

  - Add tests.

## License

BSD / MIT

## Author Information

This role was created in 2017 by [Dmytro Danylevskyi](http://dmytro.danylevskyi.com/).
