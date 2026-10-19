# Metis

Hardware monitoring for Windows PCs and servers: a small agent on each machine, and one dashboard that shows their temperatures,
load, memory and disk health. It runs on your own network. Free for up to 5 machines.

**Product page, pricing and help:** https://metis.fungusware.com

## Download

Get the latest files from the [Releases page](https://github.com/Fungusware/Metis/releases/latest):

| File | What it is |
|---|---|
| `Metis-Dashboard-win-x64.zip` | The dashboard. Install it once, on one Windows machine. |
| `Metis-Agent-win-x64.zip` | The agent. Install it on each machine you want to watch. |

Both need Windows 10 (1607) or Windows Server 2016 or newer, 64-bit. Unzip, open PowerShell as Administrator in the folder,
and run `Install-MetisDashboard.ps1` or `Install-MetisAgent.ps1`. Each zip has a `README.txt` with the options.

This repository only carries the releases. Help: https://support.fungusware.com
