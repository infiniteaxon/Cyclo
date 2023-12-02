
### What to Harden?
- Physical Security
- Filesystem Encryption
- Firewall Configuration
- Remote Access
- Software and Services
- Updates and Upgrades
- Logs


### SECCDC Plan

- Segment Apache server from rest of filesystem
  - Could user Kubernets and self-heal based on income parameters?
- Use SELinux, AppArmor, or other to restrict 80/443 to /usr/bin/apache2
- Disable RA as root and specify allowed RA accts, use PKI ! passwords
