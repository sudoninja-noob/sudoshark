<div align="center">

```
 ███████╗██╗   ██╗██████╗  ██████╗ ███████╗██╗  ██╗ █████╗ ██████╗ ██╗  ██╗
 ██╔════╝██║   ██║██╔══██╗██╔═══██╗██╔════╝██║  ██║██╔══██╗██╔══██╗██║ ██╔╝
 ███████╗██║   ██║██║  ██║██║   ██║███████╗███████║███████║██████╔╝█████╔╝ 
 ╚════██║██║   ██║██║  ██║██║   ██║╚════██║██╔══██║██╔══██║██╔══██╗██╔═██╗ 
 ███████║╚██████╔╝██████╔╝╚██████╔╝███████║██║  ██║██║  ██║██║  ██║██║  ██╗
 ╚══════╝ ╚═════╝ ╚═════╝  ╚═════╝ ╚══════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝
```

**🦈 SudoShark — Professional PCAP Security Analyzer**

[![Author](https://img.shields.io/badge/author-%40sudoninja-00c8ff?style=flat-square)](https://github.com/sudoninja-noob)
[![Version](https://img.shields.io/badge/version-2.0.0-00c8ff?style=flat-square)]()
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)]()
[![Zero deps](https://img.shields.io/badge/dependencies-zero-brightgreen?style=flat-square)]()
[![Single file](https://img.shields.io/badge/delivery-single%20HTML%20file-blue?style=flat-square)]()
[![Privacy](https://img.shields.io/badge/privacy-100%25%20local%2C%20no%20upload-green?style=flat-square)]()

*Built by [@sudoninja](https://github.com/sudoninja-noob) · Senior Manager, Cyber Security Services · SGS Brightsight*

</div>

---

## 🎬 Demo

<div align="center">

[![SudoShark Demo](https://img.youtube.com/vi/pSG-5ELB8uE/maxresdefault.jpg)](https://youtu.be/pSG-5ELB8uE)

**▶ [Watch the full demo on YouTube](https://youtu.be/pSG-5ELB8uE)**

*PCAP loading · Protocol analysis · Credential harvesting · Animated Explainer · Report generation*

</div>

---

## What is SudoShark?

SudoShark is a **zero-dependency, single-file HTML PCAP analyzer** built for security engineers, TIC labs, and telecom/IoT security assessors. Drop it in a browser, load any `.pcap` or `.pcapng` file, and get instant deep packet analysis — no server, no upload, no install.

Built specifically for professionals working with **EN 303 645**, **3GPP TS 33.117**, **GSMA FS.11**, **IEC 62443**, **ISO/SAE 21434**, and **UN R155/R156** standards.

---

## ✨ Features

### 🔍 Deep Protocol Dissection — 75+ protocols

| Layer | Protocols |
|-------|-----------|
| **L2 Data Link** | Ethernet, 802.1Q VLAN, ARP, LLDP, LACP, CDP, STP/RSTP/MSTP, PPPoE, MPLS |
| **L3 Network** | IPv4, IPv6, ICMP (full type table), ICMPv6, OSPF, GRE, ESP, AH, VRRP |
| **L4 Transport** | TCP (full flags + scan detection), UDP, SCTP (chunks + PPID sniffing) |
| **Application** | HTTP, HTTPS/TLS (cipher audit), SSH, FTP/FTP-Data, SMTP, POP3, IMAP |
| **DNS/Discovery** | DNS, mDNS, DHCP (full DORA), DHCPv6, NTP (full), SNMP, Syslog, TFTP |
| **Routing** | BGP (full: OPEN/UPDATE/NOTIFICATION + AS_PATH), OSPF, RIP/RIPng, LDP, RSVP, BFD |
| **Tunneling/VPN** | GRE, ESP, AH, IKE/IKEv2, VXLAN, GTP-U, GTP-C (GTPv2) |
| **5G / Telecom** | SCTP, Diameter (all AVPs), GTPv2-C, PFCP (N4), PTP/IEEE 1588, NetFlow/IPFIX |
| **VoIP** | SIP (full headers + SDP), RTP (heuristic), RTCP (loss/jitter), RADIUS |
| **IoT / OT** | MQTT (topics + auth), Modbus TCP (function codes), CoAP (URIs), DNP3, BACnet |
| **Databases** | MySQL, PostgreSQL, MSSQL/TDS, Redis, MongoDB |
| **Legacy / Other** | Telnet, LDAP, VNC, IRC, rlogin, TACACS+, TPKT |

### 🔓 Credential Harvester — 20+ Protocols

Auto-extracts cleartext credentials from every protocol that carries them:

| Protocol | What is extracted |
|----------|-------------------|
| **FTP** | Username + actual password value |
| **Telnet** | Full keystroke reconstruction → username + password |
| **POP3 / IMAP** | USER + PASS commands |
| **SMTP** | AUTH LOGIN, AUTH PLAIN (base64 decoded) |
| **HTTP** | Basic Auth (decoded), Bearer tokens, form POST body, cookies/sessions, API keys in URL |
| **MQTT** | CONNECT username + password |
| **LDAP** | Bind DN + simple-bind password |
| **SNMP** | Community string (flags `public`/`private` as HIGH) |
| **RADIUS** | Username + PAP password |
| **Redis** | AUTH password |
| **MySQL / PostgreSQL** | Login usernames |
| **VNC** | DES challenge-response (flags as crackable) |
| **IRC / rlogin** | Login credentials |
| **Any other protocol** | Generic payload scanner catches `username=` / `password=` patterns in **any cleartext TCP or UDP stream** |

### 🛡 Security Analysis
- **TLS Cipher Audit** — ClientHello cipher suite analysis: weak ciphers, PFS check, TLS 1.3 support, version downgrade detection
- **Port Scan Detection** — TCP NULL, XMAS, SYN, FIN, RST scan pattern recognition
- **Protocol Security Flags** — 30+ automated checks: ICMP covert channel, DNS tunneling, BGP NOTIFICATION, STP TC storm, OSPF duplicate Router-ID, MQTT unauthenticated sessions, Modbus no-auth, ICMP redirect (MITM), IP fragmentation evasion

### 🔄 TCP Stream Reassembly
- Groups all packets into conversations by IP:port pair
- Reassemble and display full session payload (HTTP bodies, FTP sessions, POP3 emails)
- Client/server color-coded view, hex mode, copy to clipboard

### 🔍 Wireshark Display Filter Syntax
Full support for real Wireshark filter expressions:
```
ip.src == 10.0.0.1
tcp.port == 80
dns.qry.name contains "evil"
tcp.flags.syn == 1 and not tcp.flags.ack == 1
tls.handshake.type == 1
frame.len > 1000
http.request.method == "POST"
not tcp and not udp
```

### 📊 Dashboard Views (10 tabs)

| Tab | Contents |
|-----|----------|
| **📋 Packets** | Full packet table with Wireshark-style filter, detail pane, hex dump |
| **📊 Dashboard** | Capture overview, protocol distribution, packet timeline, top talkers, top flows |
| **🔄 Streams** | TCP/UDP stream reassembly, payload viewer, hex mode |
| **🔓 Credentials** | Harvested cleartext credentials table, exportable CSV |
| **🔌 IoT/OT** | MQTT topics + security, Modbus function codes, CoAP URIs, EN 303 645 compliance hints |
| **☎ VoIP** | SIP call records (INVITE→BYE), MOS estimate, RTCP loss/jitter, SIP scan detection |
| **🗺 Routing** | BGP session analysis, OSPF adjacency map, STP topology change alerts, LACP/CDP inventory |
| **📡 5G/Telecom** | 3GPP interface detection (S6a/S11/N4/fronthaul), Diameter commands, GTP TEIDs, PTP grandmaster stability, TS 33.117 compliance table |
| **📄 Report** | One-click security assessment report with all findings, TLS audit, credential table, protocol inventory |
| **🎬 Explainer** | Animated protocol handshake visualizer — shows only protocols from your capture, auto-plays with real packet data |

---

## 🚀 Usage

### Option 1 — Direct download
```bash
# Download and open in browser
curl -L https://raw.githubusercontent.com/sudoninja-noob/sudoshark/main/sudoshark.html -o sudoshark.html
open sudoshark.html        # macOS
xdg-open sudoshark.html    # Linux
```

### Option 2 — Clone and use
```bash
git clone https://github.com/sudoninja-noob/sudoshark
cd sudoshark
# Open sudoshark.html in any modern browser
```

### Option 3 — GitHub Pages
Visit: `https://sudoninja-noob.github.io/sudoshark/`

---

## 📋 Standards Coverage

| Standard | Area | Coverage |
|----------|------|----------|
| **ETSI EN 303 645** | IoT consumer device security | MQTT auth, TFTP risk, cleartext credential detection |
| **3GPP TS 33.117** | Network product security assurance | Diameter TLS, GTP-C integrity, IPsec presence |
| **GSMA FS.11** | SS7/Diameter security | Diameter roaming, peer authentication hints |
| **GSMA FS.13** | LTE/EPC security | GTP session analysis |
| **IEC 62443-4-2** | Industrial cybersecurity | Modbus no-auth, DNP3 detection |
| **ISO/SAE 21434** | Automotive cybersecurity | Network exposure analysis, protocol inventory |
| **UN R155/R156** | Vehicle cybersecurity regulation | Threat surface mapping via traffic analysis |

---

## 🏗 Architecture

```
sudoshark.html              ← single self-contained file (~230KB)
├── CSS                     ← dark theme, responsive layout, 10-tab UI
├── HTML                    ← upload screen, packet table, 10 view panels
└── JavaScript (~3500 lines)
    ├── parsePcap()         ← binary PCAP classic parser (LE/BE/NS)
    ├── parsePcapNG()       ← PCAPNG block parser (SHB/IDB/EPB/OPB/SPB)
    ├── dissect()           ← L2→L7 dissector engine
    │   ├── dissectTCP/UDP/ICMP/ICMPv6
    │   ├── dissectHTTP/TLS/SSH/FTP/SMTP/POP3/IMAP
    │   ├── dissectDNS/DHCP/NTP/SNMP/Syslog/TFTP
    │   ├── dissectBGPFull/OSPF/STP/LACP/CDP/LLDP
    │   ├── dissectSCTP/Diameter/GTPv2/PFCP/RTCP/PTP/NetFlow
    │   ├── dissectMQTT/Modbus/CoAP/DNP3/BACnet
    │   ├── dissectTLSCiphers/IKE/RADIUS/SIP/RTP/RTCP
    │   └── port detection: LDAP/MySQL/PostgreSQL/MSSQL/Redis/MongoDB/VNC/IRC/rlogin
    ├── parseWsFilter()     ← Wireshark display filter engine (AND/OR/NOT/contains)
    ├── buildStreams()       ← TCP/UDP stream reassembly
    ├── buildCredentials()  ← 20+ protocol credential harvester + generic scanner
    ├── reconstructTelnetCreds() ← character-by-character Telnet login reconstruction
    ├── buildVoIPView()     ← SIP call tracker + RTCP quality
    ├── buildRoutingView()  ← BGP/OSPF/STP health
    ├── buildTelecomView()  ← 5G/telecom + TS 33.117
    ├── buildIoTView()      ← IoT/OT + EN 303 645
    ├── buildReport()       ← assessment report generator
    ├── buildExplainerList() ← capture-driven protocol explainer
    └── exportCSV/HTML      ← export functions
```

---

## 🔒 Privacy

**SudoShark processes everything locally in your browser.** No data is uploaded anywhere. No tracking. No analytics. No CDN requests at runtime (fonts load from Google Fonts on first open only — remove the `<link>` tag for fully air-gapped use).

---

## 🧪 Tested With

- Wireshark official sample captures
- FTP credential capture (csanders/echo — detected ✓)
- Telnet session (Teluser/Test@123 — keystroke-reconstructed ✓)
- SSH encrypted sessions (0 credentials, correct ✓)
- ICMP ping / DHCP DORA sequences
- IoT MQTT broker traffic
- 4G/LTE GTP-C captures
- BGP peering sessions
- Telnet-TC2.pcapng (31 packets, 2 credentials harvested)
- Custom CTF challenges

---

## 📦 GitHub Repository Structure

```
sudoshark/
├── sudoshark.html      ← main tool (drop in browser)
├── README.md           ← this file
├── LICENSE             ← MIT
├── samples/            ← sample PCAP files for testing (optional)
│   ├── ftp-sample.pcap
│   ├── telnet-sample.pcapng
│   ├── icmp-sample.pcap
│   └── dhcp-sample.pcap
└── screenshots/        ← UI screenshots (optional)
```

---

## 🤝 Contributing

PRs welcome. Key areas:
- Additional protocol dissectors (EtherNet/IP, PROFINET, IEC 61850 GOOSE, SOME/IP, DoIP)
- More Wireshark display filter fields
- Performance (virtual scrolling for 100K+ packet captures)
- Additional automotive protocols (ISO 21434 / UN R155 scope)

---

## 👤 Author

**@sudoninja** · Sanjay
Senior Manager, Cyber Security Services — SGS Brightsight (formerly Granite River Labs)
Bengaluru, India

- 🐙 GitHub: [@sudoninja-noob](https://github.com/sudoninja-noob)
- 🎬 YouTube: [Demo video](https://youtu.be/pSG-5ELB8uE)
- 🔐 Domain: IoT · Automotive · Telecom · AI/LLM Security
- 📜 Certs: OSCP · CRTP · CEH · CPTE
- 🐛 CVEs: 100+ MITRE-assigned
- 📚 Books: 6 published on Amazon KDP

---

## 📄 License

MIT License — free to use, modify, and distribute. Attribution appreciated.

```
Copyright (c) 2026 @sudoninja

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

<div align="center">
<sub>🦈 SudoShark — Because <code>sudo</code> makes everything better</sub>
</div>
