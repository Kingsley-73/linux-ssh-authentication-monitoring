# SSH Authentication Investigation 

## Objective

Investigate SSH authentication events on a linux system and identify successful and failed login attempts.

## Enviroment

- Operating System: Ubuntu Linux
- Service: OpenSSH
- Protocol: SSH
- SSH Port: 22
- Lab Enviroment: VirtualBox
- Investigation Type: Authentication monitoring

## Investiagtion Performed

Reviewed SSH authentication events using sytemd journal logs.

Commands used:

```bash
sudo journalctl ~u ssh.service --no-pager -n 30
sudo journalctl ~u ssh.service --no-pager | grep "Failed password"
sudo journalctl ~u ssh.service --no-pager | grep "Accepted password"
sudo journalctl ~u ssh.service --no-pager | grep "authentication failure"
