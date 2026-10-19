# Metis

Hardware monitoring for Windows and Linux machines: a small agent on each machine, and one dashboard (it runs on Windows) that
shows their temperatures, load, memory and disk health. It runs on your own network. Free for up to 5 machines.

**Product page, pricing and help:** https://metis.fungusware.com

## Download

Get the latest files from the [Releases page](https://github.com/Fungusware/Metis/releases/latest):

| File | What it is |
|---|---|
| `Metis-Dashboard-win-x64.zip` | The dashboard. Install it once, on one Windows machine. |
| `Metis-Agent-win-x64.zip` | The agent for Windows. Install it on each Windows machine you want to watch. |
| `Metis-Agent-linux-x64.tar.gz` | The agent for Linux PCs and servers (64-bit Intel and AMD). |
| `Metis-Agent-linux-arm64.tar.gz` | The agent for 64-bit ARM Linux, such as a Raspberry Pi 4 or 5. |

The dashboard and the Windows agent need Windows 10 (1607) or Windows Server 2016 or newer, 64-bit. Unzip, open PowerShell as
Administrator in the folder, and run `Install-MetisDashboard.ps1` or `Install-MetisAgent.ps1`.

The Linux agent needs systemd, and OpenSSL, which nearly every current distribution has. Unpack it with `tar -xzf`, then run
`sudo ./install-metis-agent.sh`. Not sure which Linux file you need? Run `uname -m`: `x86_64` is x64, and `aarch64` is arm64.

Each package has a `README.txt` with the options.

This repository only carries the releases. Help: https://support.fungusware.com
