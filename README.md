<h1 align="center">ScsUnitTypeCheckIgnore</h1>
<p align="center"><b>Bypass ETS2 / ATS Attribute Type Check (SCSUnitTypeCheck)</b></p>

<p align="center">
    <a href="https://modsfire.com/UYSPa1ft7d2q65U">
        <img alt="Download" src="https://img.shields.io/badge/Download-Here-blue?style=for-the-badge">
    </a>
</p>

---

## 📦 Overview

**ScsUnitTypeCheckIgnore/ScsUnitTypeCheckBypass** is a telemetry plugin for *Euro Truck Simulator 2* and *American Truck Simulator* that patches the game in-memory to **bypass the SCS Unit Attribute Type Check**.

This allows you to load modified or non-standard save files and unit data without triggering validation errors. Such as loading local mods from the bus_job_log

---

## 🖥 How It Works

- Hooks into the game via the official **SCS Telemetry SDK**.
- Locates the **attribute type check** jump instruction at runtime.
- Patches the instruction to **disable** strict type checking.
- Restores the original code safely on shutdown.

---

## ⚙️ Features

- **Automatic detection** of the check address at runtime (pattern scan).
- **Clean patching** using `VirtualProtect` for safe memory writes.
- **No permanent modification** to the game files.
- **Support for ETS2 and ATS** (`eut2` and `amtrucks`).
- **Support for TruckersMP**
- **Safe cleanup** on plugin unload.

---

## 🧩 Plugin Usage

1. Drop the compiled DLL into your game's plugin folder:
   - `../steamapps/common/Euro Truck Simulator 2/bin/win_x64/plugins/`
   - `../steamapps/common/American Truck Simulator/bin/win_x64/plugins/`
2. Launch the game.
3. The plugin will:
   - Find the type check jump instruction.
   - Patch it.
   - Log the result to the game log.

✅ If successful, modified unit data will no longer be blocked by SCS's type checks.

---

## 📝 Important Notes

- **Safe Unload:** The plugin restores the original instruction when the game shuts down or the plugin is unloaded.
- **Game Updates:** Major game updates could change memory layouts. Always check compatibility after patches.
- **Use Responsibly:** Bypassing integrity checks may cause unintended behavior if data is heavily malformed.
