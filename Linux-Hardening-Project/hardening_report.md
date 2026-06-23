# Linux System Hardening Report

**Author:** [Your Name]  
**Date:** June 23, 2026  
**Environment:** Kali Linux / Ubuntu Lab VM  
**Objective:** Reduce attack surface by disabling unnecessary services, tightening access controls, and configuring basic defenses.

## Executive Summary
This report documents the hardening process applied to a Linux system. Key improvements include service minimization, user account cleanup, SSH security enhancements, and firewall configuration. These changes significantly reduce the system's exposure to common threats.

## 1. Service Review

**Before Hardening:**
```bash
systemctl list-unit-files --type=service | grep enabled
```

**Actions Taken:**
```bash
# Disable unnecessary services
sudo systemctl stop avahi-daemon && sudo systemctl disable avahi-daemon
sudo systemctl stop cups && sudo systemctl disable cups
sudo systemctl stop bluetooth && sudo systemctl disable bluetooth

# Mask services for added security
sudo systemctl mask avahi-daemon
```

**After Hardening:**
- Reduced running services from ~X to ~Y
- Eliminated mDNS, printing, and Bluetooth services that are rarely needed on servers.

## 2. User Account Audit

**Commands Executed:**
```bash
# Review accounts
cat /etc/passwd | grep -E 'bash|sh'

# Remove guest account
sudo userdel -r guest 2>/dev/null || echo "Guest account not found"

# Lock unused accounts
sudo usermod -L testuser

# Review sudo privileges
sudo cat /etc/sudoers.d/* || sudo cat /etc/sudoers | grep -E 'NOPASSWD|ALL'
```

**Results:**
- Removed unnecessary `guest` account.
- Locked `testuser`.
- Ensured only authorized users have sudo access.

## 3. SSH Configuration Hardening

**Edited `/etc/ssh/sshd_config`:**
```bash
# Key changes:
PermitRootLogin no
PasswordAuthentication no
PubkeyAuthentication yes
AllowUsers yourusername
PermitEmptyPasswords no
MaxAuthTries 3
LoginGraceTime 30
```

**Apply Changes:**
```bash
sudo systemctl restart sshd
sudo systemctl status sshd
```

**Verification:**
```bash
sudo sshd -t          # Config syntax check
ss -tuln | grep 22    # Confirm SSH listening
```

## 4. Firewall Configuration (UFW)

**Setup:**
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 22/tcp          # SSH
sudo ufw allow 80/tcp          # HTTP
sudo ufw allow 443/tcp         # HTTPS
sudo ufw enable
sudo ufw status verbose
```

**Rules Summary:**
- Default: Deny incoming, Allow outgoing
- Allowed: Only SSH, HTTP, HTTPS

## 5. Additional Hardening Measures (Recommended)

- Updated system: `sudo apt update && sudo apt upgrade -y`
- Disabled IPv6 if not needed
- Enabled automatic security updates
- Reviewed file permissions (`find / -perm -4000` for SUID files)

## Before vs After Observations

| Area              | Before                  | After                     | Improvement                  |
|-------------------|-------------------------|---------------------------|------------------------------|
| Running Services  | Many unnecessary        | Minimized                 | Reduced attack surface       |
| SSH Access        | Root + Password allowed | Key-only, specific users  | Strong authentication        |
| Firewall          | Disabled / permissive   | Strict deny-by-default    | Network exposure minimized   |
| User Accounts     | Unused accounts active  | Cleaned & locked          | Better privilege management  |

## Conclusion & Lessons Learned
This hardening exercise demonstrated that simple, systematic configuration changes can dramatically improve a Linux system's security posture. Key takeaway: **"Less is more"** — minimizing services and access paths is one of the most effective defenses.

**Future Enhancements:**
- Implement Fail2Ban
- Configure AppArmor / SELinux
- Enable auditd logging
- Regular vulnerability scanning (Lynis, OpenVAS)

---

**Project Status:** Complete ✅  
**Portfolio Value:** High — shows practical Linux administration and security mindset.
