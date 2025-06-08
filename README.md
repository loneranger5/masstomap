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
```
=======

### NOTE ###
This tool will create 3 report files per IP/target (text, grepable, xml). All those files will be merged automatically in the end. Don't freak out.

### FILES

This tool will generate 4 files:<br>
<br>
```
<given-report-name>.new - a new masscan report using different notation (ip:port1,port2,portN) so you can run your own (custom) nmap scanning whenever you need.
<given-report-name>.nmap.grepable - a grepable nmap report
<given-report-name>.nmap.text - a standard text nmap report
<given-report-name>.nmap.xml - a xml formated nmap report
<given-report-name>.nmap.html - NMAP Bootstrapped html file.

```




### EXAMPLE:
<br>
First, masscan:<br>
<br>

```
$ sudo masscan -p1-65535 --rate 1000 --open -oL output.masscan <target>
```


### NMAP SCRIPTS:

This tool needs nmap in the $PATH so it can be executed, and by default, the following nmap scripts should be executed:
- http-title
- http-server-header
- http-robots.txt
- http-open-proxy
- http-methods
- http-headers
- http-internal-ip-disclosure




