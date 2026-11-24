# Yair-PerfMon-ReliableCSV

A Performance Monitor template for restricted or zero-trust enterprise environments where PowerShell and other diagnostic tools can't be used to find the root cause of a problem. It records system and process activity to CSV files for 12 hours.

## What it collects

| Interval | Data |
|---|---|
| 5 seconds | CPU, memory and disk activity |
| 10 seconds | Network traffic, process CPU usage, process IDs |
| 15 seconds | Process memory and disk I/O |
| 300 seconds | Total physical memory |

## Output

`%systemdrive%\PerfLogs\Yair-PerfMon-ReliableCSV\yyyyMMdd-NNNNNN`

## How to use

1. Open Performance Monitor (`perfmon`) as Administrator.
2. Go to Data Collector Sets -> User Defined, right-click -> New -> Data Collector Set.
3. Choose "Create from a template", click Browse, and select `Yair-PerfMon-ReliableCSV.xml`.
4. Finish, then right-click the new set and choose Start.
5. It runs for up to 12 hours. Logs are written as CSV files under `%systemdrive%\PerfLogs\Yair-PerfMon-ReliableCSV\yyyyMMdd-NNNNNN`.

## Notes

- Match process IDs with the other process logs to tell duplicate process names apart.
- Automatic cleanup is off and logging runs up to 12 hours, so keep an eye on free disk space.
- When collection finishes, analyze the CSV files with your organization's approved tools (for example, Excel, Power BI or an approved AI assistant).