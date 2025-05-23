## OWASP Dependency-Check report Vulnerabilities Extractor and Sorter.

This Python script processes a Dependency-Check report.json file to extract and organize vulnerability data. It produces a structured JSON report and an optional severity-level histogram.

- Extracts unique vulnerabilities by name and severity
- Sorts vulnerabilities by severity (CRITICAL → UNKNOWN)
- Handles missing or malformed data 
- Generates a vulnerability severity histogram
- Supports filtering by vulnerability source (e.g., NVD, OSSINDEX, etc.)

Requirements:
	Python 3.11+
	
Tested on Windows 11 24H2 and macOS 15.4

### usage: 

vulnerability_report_parser.py \[-h\] \[-o OUTPUT\] \[-g HISTOGRAM\] \[-s SOURCE\] input

### positional arguments:
  input                 Path to input file.

### options:
  -h, --help            show this help message and exit
  -o OUTPUT, --output OUTPUT
                        Path to output file (optional), if empty - report will be shown in runtime window).
  -g HISTOGRAM, --histogram HISTOGRAM
                        Path to output histogram file (optional, if empty - histogram will be shown in runtime
                        window).
  -s SOURCE, --source SOURCE
                        Source of vulnerabilities data "NVD", "OSSINDEX", "RETIREJS", "NPM" (optional, default -
                        "NVD").
						
### example:

python Exercise_2_vulnerability_report_parser.py report.json -o vulns.json -g histogram.json -s NVD
