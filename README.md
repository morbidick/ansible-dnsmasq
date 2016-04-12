# Dnsmasq

An Ansible role for setting up Dnsmasq under Ubuntu as local DNS and DHCP server.

## Role Variables

None of the variables below are required, but you need to at least set `dnsmasq_listen_address` to make the service available on the network.

| Variable                 | Default   | Comments |
| :---                     | :---      | :--- |
| `dnsmasq_addn_hosts`     | -         | set this to specify a custom host file that should be read in addition to `/etc/hosts`. |
| `dnsmasq_authoritative`  | `false`   | when `true`, dnsmasq will function as an authoritative name server. |
| `dnsmasq_bogus_priv`     | `false`   | set this if Dnsmasq should not forward addresses in the non-routed address spaces. |
| `dnsmasq_dhcp_hosts`     | -         | set this to reserve IP addresses for specific hosts. You should provide an array of hashes with keys `name` (optional), `mac` and `ip` for eachi reservation. |
| `dnsmasq_dhcp_ranges`    | -         | set this to enable the DHCP server. You should specify an array of hashes (with keys `start_addr`, `end_addr`, and `lease_time`) for each address pool. |
| `dnsmasq_domain_needed`  | `false`   | set this if Dnsmasq should not forward local requests (i.e. without domain name). |
| `dnsmasq_domain`         | -         | set the domain for Dnsmasq. |
| `dnsmasq_expand_hosts`   | `false`   | set this (and `dnsmasq_domain`) if you want to have a domain automatically added to simple names in a hosts-file. |
| `dnsmasq_listen_address` | 127.0.0.1 | set this to specify the IP address of the interface that should listen to DNS/DHCP requests. |
| `dnsmasq_interface`      | -         | set this to specify the the interface that should listen to DNS/DHCP requests. |
| `dnsmasq_option_router`  | -         | set this to specify the default gateway to be sent to clients. |
| `dnsmasq_port`           | -         | set this to listen on a custom port. |
| `dnsmasq_resolv_file`    | -         | set this to specify a custom `resolv.conf` file. |
| `dnsmasq_server`         | -         | set this to specify the IP address of upstream DNS servers directly. |

## Thanks to

- [Bert Van Vreckem](https://github.com/bertvv/ansible-dnsmasq) <bert.vanvreckem@gmail.com> where i shamelessly [stole](https://github.com/bertvv/ansible-dnsmasq) the basic repo setup
