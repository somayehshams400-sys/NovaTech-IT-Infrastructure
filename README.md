# NovaTech IT Infrastructure

## Project Overview

This project demonstrates the design, implementation, configuration and security of a small enterprise IT infrastructure for NovaTech Solutions.

The environment was built using Windows Server, Windows 11, Ubuntu, Active Directory, DNS, DHCP, IIS, VPN, RDP, WSUS, Group Policy, network shares and Cisco networking equipment.

## Environment

| Component | Configuration |
|---|---|
| Domain | `novatech.local` |
| Server | `SRV01` |
| Client | `PC-01` |
| LAN Network | `192.168.10.0/24` |
| Server IP | `192.168.10.10` |
| Gateway | `192.168.10.1` |
| VPN Network | `192.168.20.0/24` |
| VPN Pool | `192.168.20.200 - 192.168.20.220` |

## Main Services

- Active Directory Domain Services
- DNS
- DHCP
- IIS Web Server
- File Server
- Group Policy
- Network Shares
- VPN / RRAS
- Remote Desktop
- WSUS
- Microsoft Defender
- Automated Backup
- Automatic Network Drive Mapping
- LibreOffice Deployment
- Cisco Router and Switch Configuration

## Network

The internal network uses the `192.168.10.0/24` subnet.

The server `SRV01` provides central network and domain services. The Cisco router provides gateway and Internet connectivity.

A separate `192.168.20.0/24` network was configured for VPN clients.

See the [Network](./Network) folder for the network diagram, IP plan and topology documentation.

## Windows Server

`SRV01` was configured as the Domain Controller for:

`novatech.local`

The server provides:

- Active Directory
- DNS
- DHCP
- File Sharing
- IIS
- VPN
- WSUS
- Group Policy
- Remote Desktop

See the [Windows-Server](./Windows-Server) folder.

## Router

The Cisco router was configured with:

- Hostname
- Enable Secret
- Local administrator
- SSH version 2
- RSA keys
- MOTD banner
- LAN interface
- WAN DHCP
- NAT/PAT
- Access Control List

See the [Router](./Router) folder.

## Switch

The Cisco switch was configured with:

- Hostname
- VLAN 1 management interface
- Management IP
- Default gateway
- Local administrator
- SSH version 2
- RSA keys
- MOTD banner
- Secure VTY access

See the [Switch](./Switch) folder.

## Security

Security measures included:

- Active Directory authentication
- Group Policy restrictions
- NTFS permissions
- Share permissions
- Microsoft Defender
- VPN authentication
- Windows Firewall configuration
- SSH instead of Telnet
- Remote Desktop with NLA
- WSUS
- Automated backup

## Automation

Several tasks were automated using scripts and Group Policy.

These included:

- Automatic network drive mapping
- User data backup
- LibreOffice installation
- Wallpaper deployment

The network drive mapping script automatically assigns:

- **H:** Personal user drive
- **Z:** Common shared drive
- **Y:** Department drive

The department drive is selected based on the user's Active Directory OU.

## Challenges

Several technical problems were encountered during the project.

Examples include:

- Windows Server 2025 display problem
- Router WAN mode configuration
- Incorrect department drive mapping
- RRAS registration problem
- VPN firewall rules
- VPN/LAN subnet overlap
- RDP user permissions
- LibreOffice MSI deployment

The problems and their solutions are documented in the project report.

## Documentation

Detailed documentation can be found in the `Documentation` folder.

## Project Result

The final solution provides a functional domain-based enterprise environment where clients can authenticate against Active Directory, receive network configuration through DHCP, access shared resources, connect through VPN and RDP, receive Group Policy settings and use automated network services.

## Repository Structure

```text
/
├── Network/
├── Windows-Server/
├── Router/
├── Switch/
├── Documentation/
└── README.md
```
