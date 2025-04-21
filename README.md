# whoAMiP
This Python script securely retrieves and analyzes network information, including public and private IP addresses, subnet masks, TOR network usage, open ports, and offers an option to save results for export, tailored for Debian distros of Linux with privacy-focused enhancements.

V2 update notes:
Key Enhancements Added:
Network Interface Selection: Users can specify the network interface (default: eth0).

Multi-threaded Port Scanning: Improved speed with threading.

Advanced TOR Detection: Checks TOR usage more robustly.

Result Encryption: Encrypts output data using the cryptography library.

Dynamic Export Formats: Supports TXT, CSV, and JSON exports.

Email Notifications: Sends results via email for monitoring purposes.

Network Visualization: Visualizes open ports using matplotlib.

Custom Port Range: Allows flexible port scanning range.

Improved Error Handling: Exception handling for reliable script execution.

Secure Metadata: Limits metadata exposure during API requests.

note:
This script enhances network security by providing critical insights into a network's status and potential vulnerabilities. By identifying public and private IP addresses, subnet masks, and open ports, you can gain a comprehensive understanding of your network's configuration, which helps detect unauthorized access points or misconfigurations. The TOR usage check ensures you're aware of any potential anonymity network connections that could be exploited for malicious purposes. Additionally, with the privacy-focused enhancements like secure requests, minimal metadata sharing, and optional encrypted exports, the script reduces the risk of data exposure during scanning and data handling processes. Such tools are valuable for proactively assessing and tightening your network's defenses.

# whoAMiP
(Network Information & Security Assessment) Script

## Overview
This Python script is designed to gather essential network information, assess security vulnerabilities, and perform network diagnostics on Parrot OS (Debian-based Linux). The script retrieves public and private IP addresses, subnet masks, open ports, and checks for TOR network usage. It includes security enhancements to ensure scanning privacy and allows users to export results in CSV or TXT format for analysis and documentation.

## Features
1. **Retrieve Public IP Addresses (IPv4 & IPv6)**: Uses secure APIs to fetch public-facing IP addresses.
2. **Determine Private IP Address and Subnet Mask**: Extracts local network information.
3. **Check for TOR Network Usage**: Verifies whether a TOR exit node is being used.
4. **Scan Open Ports**: Identifies active ports on your home network.
5. **Export Results**: Saves scan output in user-friendly CSV or TXT formats.
6. **Privacy & Security Enhancements**:
   - Secure HTTPS connections
   - Limited metadata exposure
   - Optional encryption for saved results

## Requirements
- Parrot OS (Debian-based Linux)
- Python 3.x
- Administrator privileges (required for some tasks)
- Libraries: `requests`, `socket`, `subprocess`, `scapy`, `csv`

You can install missing libraries using pip:
```bash
sudo pip3 install requests scapy
```

## How to Use
1. Clone or download the script to your local system:
   ```bash
   git clone https://github.com/yourusername/network-security-script.git
   cd network-security-script
   ```

2. Run the script with Python:
   ```bash
   sudo python3 network_scan.py
   ```
   Note: Administrator privileges are required for port scanning.

3. Follow the on-screen output for gathered network information and security assessment results.

4. Export the results (optional):
   - To save as CSV:
     ```bash
     python3 network_scan.py --output csv
     ```
   - To save as TXT:
     ```bash
     python3 network_scan.py --output txt
     ```

## Example Output
### Console Output
```
Gathering network information...
Public IPv4: 203.0.113.12
Public IPv6: 2001:0db8:85a3:0000:0000:8a2e:0370:7334
Private IP: 192.168.1.10
Subnet Mask: 255.255.255.0
Using TOR Network: No
Open Ports: [22, 80, 443]
Results saved to scan_results.csv
```

### CSV File Example
```csv
Field,Value
Public IPv4,203.0.113.12
Public IPv6,2001:0db8:85a3:0000:0000:8a2e:0370:7334
Private IP,192.168.1.10
Subnet Mask,255.255.255.0
Using TOR Network,No
Open Ports,"22, 80, 443"
```

### TXT File Example
```
Public IPv4: 203.0.113.12
Public IPv6: 2001:0db8:85a3:0000:0000:8a2e:0370:7334
Private IP: 192.168.1.10
Subnet Mask: 255.255.255.0
Using TOR Network: No
Open Ports: 22, 80, 443
```

## Security Enhancements
1. **Secure HTTP Connections**: Uses HTTPS for all external API requests.
2. **Restricted Metadata**: Sends minimal metadata during API calls to protect your identity.
3. **Encrypted Exports**: Optional encryption for saved files to safeguard sensitive data.
4. **Rate Limiting**: Limits network requests to avoid detection or triggering alarms.
5. **Silent Operation**: Suppresses verbose logging to maintain low profile.
6. **Admin-only Execution**: Ensures script runs only with appropriate privileges.
7. **Dynamic IP Masking**: Masks private IP in console outputs unless explicitly requested.
8. **Local-only Scanning**: Scans restricted to the local network to prevent external exposure.

## Legal and Ethical Use
Ensure you have permission to run this script in your network environment. Unauthorized scanning of devices or networks may violate institutional policies or local laws.

## Author
R.B.H. / GitHub Profile (@wifiknight45)

Acknowledgements:
Dieu ~ Microsoft Copilot ~ Google Colab ~ Visual Studio Code 

## License
This script is licensed under MIT License. You can freely modify and distribute it, provided proper attribution is maintained.

---

Let me know if you need additional tweaks, features, or enhancements! 😊
