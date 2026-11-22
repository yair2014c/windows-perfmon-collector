Yair-PerfMon-ReliableCSV

A Performance Monitor template built for zero trust enterprise environments or restricted systems where PowerShell or other diagnostic tools cannot be used to find the root cause of a problem. It records system and process activity into CSV files for 12 hours.

Output path:
%systemdrive%\PerfLogs\Yair-PerfMon-ReliableCSV\yyyyMMdd-NNNNNN

What it collects
Every 5 seconds: CPU, memory, and disk activity.
Every 10 seconds: network traffic, process CPU usage, and process IDs.
Every 15 seconds: process memory and disk I/O.
Every 300 seconds: total physical memory.

How to run (Administrator)
logman import -n "Yair-PerfMon-ReliableCSV" -xml "Yair-PerfMon-ReliableCSV.xml"
logman start -n "Yair-PerfMon-ReliableCSV"

Notes
Match process IDs with the other process logs to tell duplicate process names apart.
Automatic cleanup is off and logging runs up to 12 hours, so keep an eye on free disk space.
Once collection finishes, pass the CSV files to an agent to analyze the data and provide a full overview.
