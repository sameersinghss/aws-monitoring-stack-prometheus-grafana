docs/
│
├── ec2-setup.md
├── prometheus-installation.md
├── node-exporter-installation.md
├── grafana-installation.md
└── troubleshooting.md

**ec2-setup.md**
Launch EC2
Open ports:
22
3000
9090
9100

Connect via SSH


**prometheus-installation.md**

Prometheus installation steps
Prometheus service creation
Prometheus validation


**node-exporter-installation.md**

Download Node Exporter
Create service
Enable service
Verify metrics

**grafana-installation.md**

Install Grafana
Configure datasource
Import dashboard 1860


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
