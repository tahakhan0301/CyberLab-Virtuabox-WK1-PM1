# Troubleshooting Notes

Use the least disruptive diagnostic step first. Capture the exact error text before changing settings.

## APT reports that a lock is held

Example: `Could not get lock /var/lib/apt/lists/lock`.

1. Do not delete the lock file.
2. Check for package-management processes:

   ```bash
   ps -eo pid,ppid,stat,etime,cmd | grep -E '[a]pt|[d]pkg'
   ```

3. If an update or installation is active, let it finish.
4. If a process appears genuinely stuck, inspect its state and logs before stopping it. Avoid force-killing package tools unless you understand the consequences.
5. When no package-management process remains, retry:

   ```bash
   sudo apt update
   ```

6. If the problem continues, record the full error and investigate the process holding the lock.

## No IP address appears

1. Inspect interfaces with `ip address`.
2. Confirm the virtual adapter is enabled in VirtualBox.
3. Check the selected network mode.
4. Restart networking or reboot only after recording the current configuration and consulting version-appropriate documentation.

## Internet access appears unavailable

1. Inspect `ip route` for a default route.
2. Check whether the selected VirtualBox mode is expected to provide outbound connectivity.
3. Test a known IP separately from DNS.
4. Check host connectivity and firewall settings.
5. Remember that ping can be blocked even when other traffic works.

## DNS lookup fails

Inspect `/etc/resolv.conf`, then test a name lookup:

```bash
getent hosts example.com
```

Do not overwrite resolver configuration blindly; it may be managed by the system's network service.

## Document the resolution

Add the date, symptom, diagnostic evidence, root cause if confirmed, fix, and verification result to `LAB-NOTES.md`. Clearly label unconfirmed hypotheses.
