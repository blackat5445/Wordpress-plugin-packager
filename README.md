# 🎁 WordPress Plugin Packager

> A smart batch script that automatically packages your WordPress plugins into distribution-ready ZIP files with version control and intelligent exclusion management.

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)]()
[![WordPress](https://img.shields.io/badge/WordPress-Compatible-brightgreen.svg)]()

## ✨ Features

- 🚀 **One-Click Packaging** - Bundle your plugin with a single command
- 📦 **No Root Folder** - Files are added directly to the ZIP (WordPress.org ready)
- 🎯 **Smart Exclusions** - Automatically excludes dev files with validation
- 💾 **Persistent Configuration** - Saves settings in `packager.config`
- 🔄 **Version Auto-Detection** - Reads plugin name and version from your main PHP file
- 🎨 **Interactive Setup** - First-run wizard guides you through configuration
- ⚙️ **Settings Management** - Easy reconfiguration through built-in menu

## 📋 Requirements

- Windows OS
- PowerShell (pre-installed on Windows)
- A WordPress plugin with proper headers

## 🚀 Quick Start

### 1. Download & Place

Download `Compiler.bat` and place it in your plugin's root directory:
```
your-plugin/
├── your-plugin.php  (main plugin file)
├── Compiler.bat     (this script)
├── includes/
├── assets/
└── ...
```

### 2. First Run

Double-click `Compiler.bat`. The script will guide you through setup:

**Step 1:** Enter your main plugin file name
```
Main Plugin File: your-plugin.php
```

**Step 2:** Add files/folders to exclude (optional)
```
File/Folder: .gitignore
✓ SUCCESS: File found and added

File/Folder: tests
✓ SUCCESS: Folder found and added

Add more exclusions? (Y/N): N
```

### 3. Bundle Your Plugin

From the main menu, select option `1` to create your ZIP:
```
=========================================================
WP PLUGIN PACKAGER - MAIN MENU
=========================================================

1. Bundle Plugin
2. Settings (Reconfigure)
3. Exit

Select an option (1-3): 1
```

Your versioned ZIP will be created in the `dist` folder!

## 📖 Usage

### Main Menu Options

| Option | Description |
|--------|-------------|
| **1. Bundle Plugin** | Creates a versioned ZIP file in the `dist` folder |
| **2. Settings** | Reconfigure main file and exclusions |
| **3. Exit** | Close the packager |

### Default Exclusions

The following files/folders are always excluded:
- `.git`
- `.svn`
- `node_modules`
- `dist`
- `Compiler.bat`
- `packager.config`

### Output Example
```
dist/
└── my-awesome-plugin.1.2.5.zip
```

Inside the ZIP, files are at root level (no parent folder):
```
my-awesome-plugin.1.2.5.zip
├── my-awesome-plugin.php
├── readme.txt
├── includes/
└── assets/
```

## 🎯 How It Works

1. **Reads Plugin Headers** - Extracts plugin name and version from your main PHP file
2. **Validates Files** - Checks that files you want to exclude actually exist
3. **Creates Temp Folder** - Copies all files except exclusions to `_temp_package`
4. **Generates ZIP** - Compresses files directly (no root folder) with version number
5. **Cleans Up** - Removes temporary files automatically

## ⚠️ Troubleshooting

**Error: "ZIP FAILED: File is locked"**
- Close VS Code, Local, or any other program using plugin files
- Try again after closing editors

**Error: "Plugin Name not found in header"**
- Ensure your main PHP file has proper WordPress plugin headers:
```php
/**
 * Plugin Name: My Awesome Plugin
 * Version: 1.0.0
 */
```

## 🗺️ Roadmap

- [ ] 🐧 Linux version (Bash script)
- [ ] 🍎 macOS version (Bash script)
- [ ] 📝 Custom output directory
- [ ] 🔍 Dry-run mode (preview before packaging)
- [ ] 📊 Compression statistics

## 👨‍💻 Author

**Kasra Falahati**
- Website: [Kasra.eu](https://kasra.eu)
- Sponsored by: [Agenzia magma](https://agenziamagma.it)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/blackat5445/Wordpress-plugin-packager/issues).

---

<p align="center">Made with ❤️ for the WordPress community</p>