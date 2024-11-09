# Dirty Laundry

## Description
Points: 100  
Category: Forensics  

The challenge provides a `.pcap` file and hints at finding sensitive information from network traffic.

## Approach
The challenge seemed like it might involve Wireshark and network protocols analysis to extract sensitive data.

## Solution Steps
1. **Open the `.pcap` file in Wireshark**  
   I inspected HTTP traffic to locate sensitive information.

2. **Filter for HTTP Traffic**  
   ```shell
   http contains "password"
