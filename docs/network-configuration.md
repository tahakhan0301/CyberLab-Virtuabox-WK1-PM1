# Virtual Network Configuration

## Purpose

Document how the Kali Linux VM connects to the host and, if applicable, other lab VMs. Choose the mode based on the exercise and the required isolation.

## Common VirtualBox modes

| Mode | General behavior | Considerations |
| --- | --- | --- |
| NAT | VM typically reaches external networks through address translation | Convenient for basic outbound access; inbound access is restricted unless configured |
| NAT Network | Multiple VMs can share a NAT-based network | Useful for selected multi-VM exercises; review routing and exposure |
| Host-only | VM communicates with the host and other VMs on that host-only network | Usually suited to isolated local labs; does not normally provide internet by itself |
| Bridged | VM appears on the physical network through the host's network adapter | Use caution; the VM may be reachable by other devices on the LAN |

Behavior depends on host networking, firewall rules, and VirtualBox configuration. Review official documentation before changing modes.

## Configuration workflow

1. Shut down the VM before changing adapter settings when practical.
2. Open VM **Settings → Network**.
3. Select the adapter and mode appropriate to your lab.
4. Start the VM and inspect the interface:

   ```bash
   ip address
   ```

5. Inspect the routing table:

   ```bash
   ip route
   ```

6. Inspect resolver configuration:

   ```bash
   cat /etc/resolv.conf
   ```

7. Record the mode and observed values in `LAB-NOTES.md`.

## Connectivity checks

If the lab is expected to have outbound internet access, test the layers separately:

```bash
ip route
ping -c 4 1.1.1.1
getent hosts example.com
```

- A route indicates how traffic may be directed; it does not prove the route works.
- A successful IP test does not prove DNS is working.
- A failed ping can be caused by ICMP filtering, so use more than one indicator.

## Record the actual setup

- VirtualBox version:
- VM name:
- Adapter mode:
- Interface name:
- IP address/subnet:
- Default gateway:
- DNS resolver:
- Tests performed:
- Results and date:
