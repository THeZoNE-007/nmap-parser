# Network Scanner Tool

## Overview

This Python script automates network scanning using **Nmap** to discover devices on a network, their MAC addresses, and the status of specified ports. It generates a CSV report containing details about each device, including IP address, MAC address, and the status of scanned ports (e.g., open, closed, filtered). This tool is useful for network reconnaissance and security assessments.

---

## Features

### Key Functionality
1. **Device Discovery**:
   - Scans the network to identify active devices.
   - Retrieves the IP address and MAC address of each device.

2. **Port Status**:
   - Checks the status of user-specified ports (e.g., 80, 443, 22) for each device.
   - Reports whether each port is open, closed, or filtered, along with the associated service.

3. **CSV Output**:
   - Generates a CSV file (`output.csv`) summarizing the results for further analysis.

---

## Requirements

### Prerequisites
- Python 3.x
- Required tools installed on your system:
  - [Nmap](https://nmap.org/)

### Installation
1. Install Nmap:
   ```bash
   sudo apt-get install nmap
   ```

2. Clone this repository:
   ```bash
   git clone "https://github.com/THeZoNE-007/nmap-parser.git"
   cd nmap-parser
   ```

---

## Usage

### Running the Script
1. Run the script and provide the network range when prompted:
   ```bash
   python NMAP_parser.py
   ```

2. Enter the network range in CIDR notation (e.g., `192.168.1.0/24`).

3. Specify the ports you want to scan. Enter `-1` to stop adding ports.

4. The script will execute the Nmap scan and generate a CSV file (`output.csv`) in the same directory.

---

## Example Commands

### Input Example
```
Enter a ip address/cidr: 192.168.1.0/24
Enter a port no.: press -1 to break: 80
Enter a port no.: press -1 to break: 443
Enter a port no.: press -1 to break: 22
Enter a port no.: press -1 to break: -1
```

### Output Example
The generated `output.csv` will contain entries like this:
```
{'IP': '192.168.1.1', 'MAC': '00:1A:2B:3C:4D:5E', '80': 'open service=http', '443': 'closed service=https', '22': 'filtered service=ssh'}
{'IP': '192.168.1.2', 'MAC': 'Unknown', '80': 'not found', '443': 'not found', '22': 'not found'}
```

---

## Notes

1. **Permissions**: Nmap requires root privileges. Ensure the script is executed with `sudo` if necessary.
2. **Output File**: The script appends results to `output.csv`. If the file already exists, new results will be added to it.
3. **Port Status**:
   - Ports not found in the scan are marked as `"not found"`.
   - The status includes whether the port is `open`, `closed`, or `filtered`, along with the associated service.

---

## Acknowledgments

- Built using the [Nmap](https://nmap.org/) tool for network scanning.
- Designed for use in network reconnaissance and security assessments.
