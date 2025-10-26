# PluginSmith – Multi-Engine Plugin Builder

**Version:** 5.5  
**Author:** AlphaCore  
**Website:** https://support.alphaxp.me  
**Fab Listing:** [https://www.fab.com/portal/listings/](https://www.fab.com/portal/listings/bb1a7ad5-934f-42a8-b133-e4591edfda49/preview)  
**Supported Engines:** Unreal Engine 4.27 – 5.5  
**Supported Platforms:** Windows (Win64)

---

## Overview
PluginSmith automates packaging, validation, and multi-engine compatibility building for Unreal Engine projects and plugins. It is designed for plugin developers and marketplace publishers who need to build once and deploy across multiple Unreal Engine versions quickly and safely.

PluginSmith can package plugins or entire UE projects for different engine versions, generate Fab-compliant `.zip` archives, log all build and packaging steps, validate engine versions, and handle editor or runtime modules. It provides a full API for Blueprint and command-line automation.

---

## Features
- Multi-engine packaging support (UE 4.27 → 5.5)
- Automatic Fab-compliant `.zip` generation
- Built-in `.uplugin` validation for engine version, documentation, and platform lists
- Logging system with readable text logs in `Saved/Logs/PluginSmith.log`
- CLI and Blueprint automation APIs
- Automatic cleanup of non-distributable folders (Binaries, Intermediate, Saved)
- Docs and metadata inclusion during packaging
- Ready-to-submit folder and version structure for Fab marketplace

---

## Installation and Setup
1. Copy the `PluginSmith` folder into your project’s `Plugins` directory.
2. Open your Unreal Engine project in any supported version (4.27 – 5.5).
3. Go to `Edit → Plugins`, enable **PluginSmith – Multi-Engine Plugin Builder**, then restart the editor.
4. Once loaded, PluginSmith adds a “PluginSmith” section under **Tools** in the main menu.

---

## Usage

### Packaging via Editor
1. Go to **Tools → PluginSmith → Build Plugin**.  
2. Choose your:
   - Target Engine Version
   - Output Directory
   - Package Type (Plugin / Project)
   - Whether to include documentation
3. Click **Build**. PluginSmith validates the plugin, cleans intermediate files, and creates a ready-to-upload `.zip` archive for Fab.

### Packaging via Command Line
You can run PluginSmith in headless mode from Unreal’s command-line interface:

```powershell
UE4Editor-Cmd.exe "C:\YourProject\YourProject.uproject" -run=PluginSmithBuild -Target=5.5 -Output="C:\Builds"




PluginSmith/
 ├── PluginSmith.uplugin
 ├── Source/
 │   └── PluginSmith/
 │       ├── Public/
 │       │   ├── PluginSmithBPLibrary.h
 │       │   └── PluginSmithManager.h
 │       └── Private/
 │           ├── PluginSmithBPLibrary.cpp
 │           ├── PluginSmithManager.cpp
 │           └── PluginSmithModule.cpp
 ├── Config/
 ├── Resources/
 └── Saved/Logs/
