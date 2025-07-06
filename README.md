# Splunk Home Lab Setup

## Overview

This project documents our process of installing and configuring Splunk Enterprise on Kali Linux as a home SIEM (Security Information and Event Management) lab. The goal is to gain hands on experience with Splunk, practice log analysis, and build a foundation for advanced security monitoring.

---

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Installation Steps](#installation-steps)
- [Initial Configuration](#initial-configuration)
- [Troubleshooting](#troubleshooting)
- [Lessons Learned](#lessons-learned)
- [Next Steps](#next-steps)
- [Resources](#resources)

---

## Requirements

- **Host Hardware:** Ryzen 5 7600, 64GB RAM, RX 6950XT
- **Virtualization:** VirtualBox VM running Kali Linux
- **VM Resources:** 4–6 CPU cores, 8–16GB RAM, 50GB+ disk
- **Splunk Version:** Latest (downloaded from official site)
- **Network:** Local network access for log forwarding and web interface

---

## Installation Steps

1. **Download Splunk Enterprise**
    - Go to [Splunk Downloads](https://www.splunk.com/en_us/download/splunk-enterprise.html)
    - Download the `.deb` package for Linux (Debian/Ubuntu)

2. **Install Splunk**
    ```
    cd ~/Downloads
    sudo dpkg -i splunk-*.deb
    ```

3. **Start Splunk**
    ```
    cd /opt/splunk/bin
    sudo ./splunk start
    ```
    - Accept the license and set up the admin username/password.

4. **(Optional) Enable Splunk at Boot**
    ```
    sudo ./splunk enable boot-start
    ```

5. **Access Splunk Web Interface**
    - Open a browser and go to: `http://localhost:8000` or `http://<VM_IP>:8000`
    - Log in with the admin credentials.

---

## Initial Configuration

- Added local log sources for testing.
- Explored the Splunk dashboard and basic search features.
- Confirmed Splunk is running and accessible from the network.

---

## Troubleshooting

- **dpkg error: No such file or directory:**  
  Make sure you download the `.deb` file and run the install command in the correct directory.
- **CPU/RAM allocation locked:**  
  Ensure the VM is powered off and virtualization is enabled in BIOS/UEFI.

---

## Lessons Learned

- Splunk is resource intensive; allocating more CPU and RAM to the VM greatly improves performance.
- Using Linux (Kali) makes installation and management easier via the terminal.
- Documenting each step even the basics helps with troubleshooting and future upgrades.

---

## Next Steps

- Add log sources from other devices (NAS, Windows PC, routers).
- Build custom dashboards and alerts for security monitoring.
- Explore Splunk apps and integrations for deeper analysis.
- Document advanced use cases and detection rules.

---

## Resources

- [Splunk Enterprise Download](https://www.splunk.com/en_us/download/splunk-enterprise.html)
- [Splunk Docs: Install on Linux](https://docs.splunk.com/Documentation/Splunk/latest/Installation/InstallonLinux)
- [Splunk Home Lab Best Practices (Reddit)](https://www.reddit.com/r/Splunk/comments/1384syv/splunk_server_home_lab/)
- [VirtualBox Documentation](https://www.virtualbox.org/manual/UserManual.html)
- [Kali Linux Documentation](https://www.kali.org/docs/)

---

*This project is part of our ongoing journey to master security operations and SIEM technologies. All feedback and collaboration welcome!*

