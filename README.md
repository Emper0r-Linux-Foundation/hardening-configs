# hardening-configs
Default firewall rules (nftables/ufw), AppArmor/SELinux profiles, and kernel sysctl security defaults.

## Kernel sysctl defaults

- `sysctl.d/99-emperor-baseline.conf`: desktop-safe kernel, filesystem, and
  network hardening. Install as `/etc/sysctl.d/99-emperor-baseline.conf`.
- `sysctl.d/99-emperor-hardened.conf`: server and Secure Boot profile. It
  disables kexec, SysRq, unprivileged user namespaces, and io_uring; do not
  ship it as the desktop default.

Apply with `sysctl --system`. Values marked with trade-offs in the files
should be verified against the supported desktop workloads.
