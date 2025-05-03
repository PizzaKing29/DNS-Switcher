# DNS Switcher (PowerShell)

This PowerShell script dynamically monitors and switches the system's DNS server to the one with the lowest average latency (ping time). It's ideal for users who want optimized DNS performance with minimal manual intervention.

## Features

- Continuously tests latency to three popular public DNS servers:
  - Google DNS: `8.8.8.8`
  - Quad9 DNS: `9.9.9.9`
  - Cloudflare DNS: `1.1.1.1`
- Automatically selects and sets the fastest DNS based on 4 ping attempts.
- Supports both Ethernet and Wi-Fi connections.
- Runs in a loop, checking and switching every 30 seconds.

## Requirements

- PowerShell (recommended: version 5.1+)
- Administrator privileges (required to change DNS settings)
- Windows operating system

## How It Works

1. Finds active network adapters with the name `Ethernet` or `Wi-Fi`.
2. Pings each of the three DNS servers four times.
3. Calculates the average response time for each.
4. Selects the DNS server with the lowest average ping.
5. Sets the selected DNS server as the active one.
6. Waits 30 seconds before repeating the process.

## Usage

1. **Open PowerShell as Administrator**
2. **Run the script**:
   ```powershell
   .\DNSSwitcher.ps1
