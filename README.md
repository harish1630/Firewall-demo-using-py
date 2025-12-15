# Firewall-demo-using-py
PacketGuard is a simple yet effective Python‑based firewall prototype designed for learning and portfolio showcase. It leverages Scapy to capture and inspect network packets in real time, applies rule‑based decisions (ALLOW/BLOCK), and logs all activity into an SQLite database for analysis.
README essentials
- What it is: A Python firewall demo for packet inspection, rule decisions, and SQLite logging. Not a kernel/OS-enforced blocker; use it to learn, analyze, and showcase.
- Features:
- Packet visibility: IP/TCP/UDP metadata capture.
- Rule engine: CIDR/IP, protocol, port-based actions (ALLOW/BLOCK/ALERT).
- Logging: SQLite with timestamps for analysis.
- CLI: Interface selection and rule loading.
- Setup:
- Windows: Install Python 3.11+, Npcap; run terminal as Administrator for sniffing.
- Linux: Ensure libpcap; consider sudo.
- Install deps: pip install -r requirements.txt
- Usage:
- python -m firewall.main --iface <iface> --rules firewall/config.yaml --db firewall_logs.db
- View logs: sqlite3 firewall_logs.db "SELECT * FROM logs ORDER BY ts DESC LIMIT 20;"
- Limitations:
- Blocking scope: This demo logs and “virtually blocks” (decision), but doesn’t drop packets at OS level.
- For real blocking: Use OS firewalls (iptables/nftables on Linux, WFP on Windows) and integrate decisions.
- Screenshots: Add CLI output and a sample log query.
- Roadmap: Stateful tracking, domain rules, export to CSV, dashboard.
