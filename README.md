# Zero Trust Network Lab — CCNA Lab Series

## Overview
A fully configured Zero Trust Network built from scratch in Cisco Packet Tracer.
Implements the "never trust, always verify" principle across three security zones
with three enforcement points.

## What was built
- 3 routers, 2 switches, 4 servers, 3 PCs
- Internet → Edge Firewall → DMZ → Core Router → Internal zones
- Serial DCE/DTE link between Edge-FW and Core-Router

## Technologies used
`Cisco IOS` `VLANs` `802.1Q Trunking` `Router-on-a-Stick`
`Named Extended ACLs` `Zero Trust Architecture` `SSH Hardening`
`Serial Interfaces` `Network Segmentation` `Packet Tracer`

## Zero Trust enforcement points
| Point | Device | Method |
|-------|--------|--------|
| ZT Point 1 | Edge-FW | Deny-all inbound ACL — permits HTTP, HTTPS, DNS to DMZ only |
| ZT Point 2 | DMZ-SW | Isolated VLAN 50 — public-facing servers only |
| ZT Point 3 | Core-Router | Inter-VLAN ACLs — Staff blocked from IT Admin, IoT blocked from all internal |

## VLAN design
| VLAN | Name | Subnet | Access |
|------|------|--------|--------|
| 10 | IT-ADMIN | 192.168.10.0/24 | Full access |
| 20 | STAFF | 192.168.20.0/24 | Limited — no VLAN 10 or 30 |
| 30 | IOT-GUEST | 192.168.30.0/24 | Internet only |
| 50 | DMZ | 192.168.50.0/24 | Public-facing only |
| 100 | SERVERS | 192.168.100.0/24 | Internal servers |

## Documentation
- [Build Guide](docs/ZeroTrust_Lab_Day1_BuildGuide.docx) — full device config, IP plan, cable table, ACLs
- [Troubleshooting Log](docs/ZeroTrust_Lab_Day1_Troubleshooting.docx) — 9 issues, root causes, resolutions, CCNA lessons

## Lab series
This is Day 1 of an ongoing CCNA lab series.
Next lab: OSPF dynamic routing replacing static routes.

## About
**Edwin Sekgethela** — Aspiring Network Engineer | CCNA Candidate August 2026
Built as part of a daily/weekly lab discipline toward CCNA certification.
