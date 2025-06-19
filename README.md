<p align="center">
  <img src="https://github.com/user-attachments/assets/873ef98a-48e0-445b-b5dc-eb5959ad5b34" width="800" />
</p>

<h1 align="center">💥 Burp Suite Professional v2025 - Automated Installer</h1>

<p align="center">
  A complete, cross-platform installer for <b>Burp Suite Professional</b> with CLI, GUI (VNC), and loader support.<br>
  Designed for Pentesters, Bug Bounty Hunters, and Ethical Hackers who want a fast setup ⚡<br><br>
  <a href="https://portswigger.net/burp/pro">🔗 Official Website</a> • 
  <a href="https://github.com/KIRAN-KUMAR-K3/BurpPro-Installer">🌐 GitHub Repo</a>
</p>

---

## 📌 Features

- 🔓 One-click installer for Linux, NixOS, and Windows
- 🔁 Auto-updater script
- 🧪 Supports manual license activation (loader support)
- 🧩 Java version selector
- 🧙 XFCE launcher creation
- 🎯 VBS shortcut support for Windows
- ❌ No root required (except on Linux for install scripts)

---

## 📥 Installation

### 💻 Linux (Debian, Ubuntu, Arch, etc.)

```bash
wget -qO- https://raw.githubusercontent.com/KIRAN-KUMAR-K3/BurpPro-Installer/main/install.sh | sudo bash
````

Then run:

```bash
burpsuitepro
```

<details>
  <summary><strong>🔄 Update Script</strong></summary>

```bash
cd ~
rm -rf BurpPro-Installer
wget -qO- https://raw.githubusercontent.com/KIRAN-KUMAR-K3/BurpPro-Installer/main/update.sh | sudo bash
```

</details>

<details>
  <summary><strong>☕ Java Version Selector</strong></summary>

```bash
sudo update-alternatives --config java
```

</details>

---

## 🔐 Manual License Activation (Loader)

> After launching Burp, go to **Manual Activation** → Copy the request key into `loader.jar` → Paste response key back into Burp.

> Video Guide:
> [https://github.com/KIRAN-KUMAR-K3/BurpPro-Installer/assets/117867334/c25831a4-68a2-44ee-b6dd-5ff18165f340](https://github.com/KIRAN-KUMAR-K3/BurpPro-Installer/assets/117867334/c25831a4-68a2-44ee-b6dd-5ff18165f340)

---

## 🧭 Linux Desktop Launcher (XFCE)

1. Right-click desktop → "Create Launcher"
2. Name: `Burp Suite Professional`
3. Command: `burpsuitepro`
4. Choose icon: `burp-suite.ico`

<p align="center">
  <img src="https://github.com/KIRAN-KUMAR-K3/BurpPro-Installer/blob/main/Launcher.jpg" width="450">
</p>

---

## 🧊 NixOS Installation (flake)

### Add this repo to your flake inputs:

```nix
{
  inputs = {
    burpsuitepro = {
      type = "github";
      owner = "KIRAN-KUMAR-K3";
      repo = "BurpPro-Installer";
      inputs.nixpkgs.follows = "nixpkgs";
    };
  };
}
```

### Use with `environment.systemPackages` or `home.packages`:

```nix
{
  environment.systemPackages = [
    inputs.burpsuitepro.packages.${system}.default
  ];
}
```

```nix
{
  home.packages = [
    inputs.burpsuitepro.packages.${system}.default
  ];
}
```

> Note: `loader.jar` is symlinked to `burpsuite.jar`

---

## 🪟 Windows Installation

1. Create a folder: `C:\Burp`
2. [Download ZIP](https://github.com/KIRAN-KUMAR-K3/BurpPro-Installer/archive/refs/heads/main.zip) and extract to `C:\Burp`
3. Open PowerShell (Admin) and run:

```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
cd C:\Burp
./install.ps1
```

4. Set the icon: Right-click `Burp-Suite-Pro.vbs` → Properties → Shortcut tab → Change Icon → `burp-suite.ico`
5. (Optional) Move shortcut to:

```txt
C:\ProgramData\Microsoft\Windows\Start Menu\Programs\
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/29830064/230825172-16c9cfba-4bca-46a4-86df-b352a4330b12.png" width="700">
</p>

---

## 📁 Project Structure

```
BurpPro-Installer/
├── install.sh
├── update.sh
├── install.ps1
├── loader.jar
├── burp_suite.ico
├── Burp-Suite-Pro.vbs
└── Launcher.jpg
```

---

## 🤝 Credits

<details>
<summary>Click to Expand</summary>

* Loader by: [h3110w0r1d-y](https://github.com/h3110w0r1d-y/BurpLoaderKeygen)
* Base script by: [cyb3rzest](https://github.com/cyb3rzest/Burp-Suite-Pro)

</details>

---

## 📜 License

This project is licensed under the **MIT License**.

> ⚠️ **Disclaimer:** This repository is for educational & research purposes only. Do not use on unauthorized systems.

---

<p align="center">
  Made with ❤️ by <a href="https://github.com/KIRAN-KUMAR-K3">Kiran Kumar K</a>
</p>
