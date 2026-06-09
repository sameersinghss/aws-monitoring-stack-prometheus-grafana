# Troubleshooting Guide

## Issue 1: SSH Timeout

Error:
ssh: connect to host port 22: Connection timed out

Root Cause:
- Incorrect Public IP
- Security Group restriction

Resolution:
- Verified EC2 Public IP
- Updated Security Group rule for SSH

---

## Issue 2: cp cannot stat

Error:
cp: cannot stat

Root Cause:
Files copied from wrong directory.

Resolution:
Changed directory to extracted Prometheus folder.

---

## Issue 3: Prometheus Service Failed

Error:
systemctl status prometheus showed failed state.

Root Cause:
Incorrect ownership on /var/lib/prometheus.

Resolution:
sudo chown -R prometheus:prometheus /var/lib/prometheus

---

## Issue 4: Disk Quota Exceeded

Error:
Cannot write to node_exporter.tar.gz

Root Cause:
Downloading to /tmp (tmpfs).

Resolution:
Downloaded file in home directory.
