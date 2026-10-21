# Metis

Hardware monitoring for Windows and Linux machines: a small agent on each machine, and one dashboard (it runs on Windows or Linux) that
shows their temperatures, load, memory and disk health. It runs on your own network. Free for up to 5 machines.

**Product page, pricing and help:** https://metis.fungusware.com

## Download

Get the latest files from the [Releases page](https://github.com/Fungusware/Metis/releases/latest):

| File | What it is |
|---|---|
| `Metis-Dashboard-win-x64.zip` | The dashboard for Windows. Install it once, on one Windows machine. |
| `Metis-Dashboard-linux-x64.tar.gz` | The dashboard for Linux PCs and servers (64-bit Intel and AMD). Install it once. |
| `Metis-Dashboard-linux-arm64.tar.gz` | The dashboard for 64-bit ARM Linux, such as a Raspberry Pi 4 or 5. |
| `Metis-Agent-win-x64.zip` | The agent for Windows. Install it on each Windows machine you want to watch. |
| `Metis-Agent-linux-x64.tar.gz` | The agent for Linux PCs and servers (64-bit Intel and AMD). |
| `Metis-Agent-linux-arm64.tar.gz` | The agent for 64-bit ARM Linux, such as a Raspberry Pi 4 or 5. |

### Quick install

One line downloads the current version and installs it.

Windows, in PowerShell as Administrator:

```powershell
irm https://metis.fungusware.com/agent.ps1 | iex
```

Linux (picks 64-bit Intel/AMD or ARM by itself):

```sh
curl -fsSL https://metis.fungusware.com/agent.sh | sudo bash
```

For the dashboard, use `dashboard.ps1` or `dashboard.sh` instead. On Linux, installer options go after `bash -s --`, for example
`curl -fsSL https://metis.fungusware.com/agent.sh | sudo bash -s -- --dashboard https://dashboard:9443`. To read a script before you run it, open its address in a browser.

### By hand

The Windows dashboard and the Windows agent need Windows 10 (1607) or Windows Server 2016 or newer, 64-bit. Unzip, open PowerShell as
Administrator in the folder, and run `.\Install-MetisDashboard.ps1` or `.\Install-MetisAgent.ps1`. If PowerShell says running
scripts is disabled, run `powershell -ExecutionPolicy Bypass -File .\Install-MetisAgent.ps1` instead (this one run only).

The Linux dashboard and agent need systemd, and OpenSSL, which nearly every current distribution has. Unpack with `tar -xzf`, then run
`sudo bash ./install-metis-dashboard.sh` or `sudo bash ./install-metis-agent.sh`. Not sure which Linux file you need? Run `uname -m`: `x86_64` is x64, and `aarch64` is arm64.

Each package has a `README.txt` with the options.

This repository only carries the releases. Help: https://support.fungusware.com
