# Please note that whoAMiP is continually being updated, check back here for the most recent update notes.  

updates--------> listed in order from most recent to least

V3 update notes 
Improved Error Handling
a) Specific exception catches (e.g., subprocess.CalledProcessError, requests.RequestException).
b) Centralized logging (levels: DEBUG, INFO, WARNING, ERROR).
c) Timeouts on all network calls to avoid hangs.
d) Validation of key file existence before loading.
e) Command-line validation (via argparse) for required parameters.

V2 update notes
a) Network Interface Selection: Users can specify the network interface (default: eth0).
b) Multi-threaded Port Scanning: Improved speed with threading.
c) Advanced TOR Detection: Checks TOR usage more robustly.
d) Result Encryption: Encrypts output data using the cryptography library.
e) Dynamic Export Formats: Supports TXT, CSV, and JSON exports.
f) Email Notifications: Sends results via email for monitoring purposes.
g) Network Visualization: Visualizes open ports using matplotlib.
h) Custom Port Range: Allows flexible port scanning range.
i) Improved Error Handling: Exception handling for reliable script execution.

# whoAMiP
Python network information & security assessment Script

## Overview
This Python script is designed to gather essential network information, assess security vulnerabilities, and perform network diagnostics on Debian-based Linux distros. The script retrieves public and private IP addresses, subnet masks, open ports, and checks for TOR network usage. It includes security enhancements to ensure scanning privacy and allows users to export results in CSV or TXT format for analysis and documentation.

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
- Linux (tested on Debian-based distros)
- Python 3.13.5 (currently the latest python stable release)
- Admin privileges (required for some tasks)
- Libraries: `requests`, `socket`, `subprocess`, `scapy`, `csv`

You can install missing libraries using pip:
bash
"sudo pip3 install requests scapy"

OR in Jupyter Notebook environment 
"!pip3 install requests scapy"


```

## How to Use
1. Clone or download the script to your local system:
   ```bash
   git clone https://github.com/wifiknight45/whoAMiP.git
   cd whoAMiP
   ```

2. Run the script with Python:
   ```bash
   sudo python3 whoAMiP.py
   ```
   Note: Administrator privileges are required for port scanning (e.g. root or sudo). 

3. Follow the on-screen output for gathered network info + SecAssess results.

4. Export the results (optional):
   a) To save as CSV:
     ```bash
     python3 whoAMiP.py --output csv
     ```
   b) To save as TXT:
     ```bash
     python3 whoAMiP.py --output txt
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

## Author
GitHub @wifiknight45
https://github.com/wifiknight45/
wifiknight45@proton.me

Acknowledgements:
Dieu

Disclaimer
This tool is provided for educational and research purposes only. The author assumes no responsibility or liability for any misuse, unintended consequences, or damages resulting from the use of this script. Users are solely responsible for ensuring that the script is utilized in compliance with all applicable laws, regulations, and organizational policies.

This script is intended only to be used in controlled environments such as test networks, virtual machines, or isolated systems. It is strongly recommended to validate its functionality in a sandboxed or non-production environment before deploying it in enterprise or private applications. Unauthorized scanning, probing, or analysis of networks or systems without proper consent is strictly prohibited and may violate legal or ethical standards.

By viewing the readme, using this tool, or modifying the source code, you are acknowledging that you a) understand and agree to these terms and that b) The author provides no warranties or guarantees regarding the performance, accuracy, or reliability of the tool/source code/script etc.

## License
This script is licensed under MIT License. You can freely modify and distribute it, provided proper attribution is maintained.

---
