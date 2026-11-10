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
| `MetisDashboard-x64-<version>.spk`, `MetisDashboard-arm64-<version>.spk` | The dashboard as a Synology DSM 7.2+ package (Package Center). |
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


### Synology DSM 7 (package)

On a Synology NAS (DSM 7.2 or newer, Intel/AMD or ARM64) install the dashboard from Package Center. In **Package Center > Settings > General**
set **Trust Level** to **Any publisher** (the package is not signed). In **Settings > Package Sources** add `https://www.fungusware.com/synology`.
Then install **Metis Dashboard** from **Community**; Package Center shows an **Update** button when a new version is out. Open `http://<nas>:9080`
(agents report to port 9443) and sign in as `metis` / `metis.metis`. You can also download `MetisDashboard-x64-<version>.spk` or
`MetisDashboard-arm64-<version>.spk` from the Releases page and use **Manual Install**. The agent is installed as on any Linux machine.

### By hand

The Windows dashboard and the Windows agent need Windows 10 (1607) or Windows Server 2016 or newer, 64-bit. Unzip, open PowerShell as
Administrator in the folder, and run `.\Install-MetisDashboard.ps1` or `.\Install-MetisAgent.ps1`. If PowerShell says running
scripts is disabled, run `powershell -ExecutionPolicy Bypass -File .\Install-MetisAgent.ps1` instead (this one run only).

The Linux dashboard and agent need systemd, and OpenSSL, which nearly every current distribution has. Unpack with `tar -xzf`, then run
`sudo bash ./install-metis-dashboard.sh` or `sudo bash ./install-metis-agent.sh`. Not sure which Linux file you need? Run `uname -m`: `x86_64` is x64, and `aarch64` is arm64.

Each package has a `README.txt` with the options.

This repository only carries the releases. Help: https://support.fungusware.com
