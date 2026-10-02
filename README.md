# Linux SSH Authentication Monitoring

## Overview

A hands-on Linux SOC lab focused on monitoring and investigating SSH authentication activity.

The project demonstrates how security analysts can review Linux authentication logs, identify failed and successful SSH login attempts, and document findings during an investigation.

## Objectives

- Monitor SSH authentication activity on a Linux system
- Identify failed authentication attempts
- Identify successful authentication events
- Review SSH service and port configuration
- Use Linux command-line tools to investigate authentication logs
- Document investigation findings
- Organize the investigation as a reproducible security lab

## Lab Environment

- Operating System: Ubuntu Linux 26.04.1 LTS
- Virtualization: VirtualBox
- Service: OpenSSH
- Protocol: SSH
- SSH Port: 22
- Environment: Local SOC Lab

## Investigation Process

The investigation used `systemd journal` logs to review SSH activity.

Key commands included:

```bash
sudo journalctl -u ssh.service --no-pager -n 30

sudo journalctl -u ssh.service --no-pager | grep "Failed password"

sudo journalctl -u ssh.service --no-pager | grep "Accepted password"

sudo journalctl -u ssh.service --no-pager | grep "authentication failure"
