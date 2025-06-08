# masstomap - Enhanced Masscan to Nmap Pipeline

masstomap is a powerful Go-based tool designed for parsing Masscan reports, running detailed Nmap scans on discovered ports, and generating rich HTML reports with Bootstrap styling. It is optimized for web service discovery and pentesting automation.

## Features

- Parses Masscan plaintext output to identify open ports.
- Runs Nmap scans on identified IP:port pairs with custom NSE scripts.
- Generates intermediate `.ixml`, `.itxt`, and `.igrep` files.
- Combines Nmap results into unified `.nmap.xml`, `.nmap.txt`, and `.nmap.grep` reports.
- Produces `.web` files listing discovered HTTP/HTTPS services.
- Converts XML reports to modern Bootstrap-styled HTML via embedded XSLT.
- Supports dry run mode for only generating target files (`.new`).

## Requirements

- **Go 1.20+**
- [Nmap](https://nmap.org/) installed and accessible in system path
- [Masscan](https://github.com/robertdavidgraham/masscan) used to generate input files

Go packages used:
- `github.com/Ullaakut/nmap/v2`
- `github.com/wamuir/go-xslt`

## Installation

Clone the repository and build:

```bash
git clone https://github.com/yourusername/masscan2nmap.git
cd masscan2nmap
go build -o masscan2nmap
