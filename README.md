# Anti-Wallhack Visibility System v1.0 - Unity Multiplayer Anti-Cheat 2026

> **Server-authoritative visibility control for Unity multiplayer games.** This Unity-based anti-cheat component performs server-side line-of-sight checks to help control wallhack-related visibility decisions in version 1.0.

[![Platform](https://img.shields.io/badge/Platform-Unity-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v1.0-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/bennettfelix22/anti-wallhack-visibility-system?style=flat-square)](https://github.com/bennettfelix22/anti-wallhack-visibility-system)

---

<p align="center">
  <a href="https://bennettfelix22.github.io/anti-wallhack-visibility-system/">
    <img src="https://img.shields.io/badge/Download-Anti-Wallhack%20Visibility%20System%20Latest-brightgreen?style=for-the-badge" alt="Download Anti-Wallhack Visibility System">
  </a>
</p>

> **[Download Anti-Wallhack Visibility System v1.0](https://bennettfelix22.github.io/anti-wallhack-visibility-system/)**

---

[Download Latest Build](https://bennettfelix22.github.io/anti-wallhack-visibility-system/)

---

## Overview

Anti-Wallhack Visibility System is a Unity multiplayer anti-cheat utility centered on server-authoritative visibility checks. It uses server-side line-of-sight evaluation to determine whether players should be considered visible, reducing dependence on client-side visibility decisions.

The component is intended for multiplayer games that need configurable detection logic in either 2D or 3D. It can be used in a range of Unity networking architectures, including Netcode for GameObjects, while giving developers control over check frequency, raycast reach, and how environmental collisions affect visibility results.

---

## Key Features

- Server-side line-of-sight checks for visibility validation
- Raycast layer control and occlusion masking
- Adjustable check interval for update frequency
- Maximum raycast distance setting
- Debug visualization for inspection and tuning
- Team-based visibility filtering
- Support for both 2D and 3D environments
- Compatibility with multiple Unity networking solutions

---

## Installation

Add the repository to your Unity project by cloning it or downloading the source directly:

- `git clone https://github.com/bennettfelix22/anti-wallhack-visibility-system.git
- or download the project files and import them into your Unity project

Once the files are in place, open the project in Unity and wire the visibility system into your multiplayer gameplay flow. For projects using Netcode for GameObjects or another supported networking layer, connect the visibility checks to server-side player state handling before starting a match.

---

## Usage

A common setup is to evaluate visibility on the server and use that result to decide whether a target should be treated as visible.

Example flow:

1. Assign the relevant target and obstacle layers.
2. Set the maximum raycast distance for your gameplay scale.
3. Choose a check interval that matches your performance needs.
4. Enable debug mode while tuning line-of-sight behavior.
5. Apply team filtering if visibility should depend on player factions.
6. Use the returned visibility result in your multiplayer logic.

Example setup outline:

- Configure the detector in a server-owned gameplay object
- Trigger visibility checks during combat or perception updates
- Use occlusion results to inform rendering, targeting, or awareness systems

---

## Configuration

Typical settings are usually available through the component or inspector:

    checkInterval: 0.2
    maxRaycastDistance: 100
    debugMode: true
    useTeamFiltering: true
    raycastLayers: "Default, Environment"
    occlusionMask: "Walls, Props"

If your project keeps configuration in a separate system, store the server-side visibility values alongside the rest of your multiplayer gameplay settings so they remain easy to tune and audit.

---

## Requirements

- Unity project
- Multiplayer or server-authoritative gameplay architecture
- A supported Unity networking solution
- Appropriate physics setup for raycast-based visibility checks
- Layer definitions for targets and occluders
- Sufficient server-side runtime resources for periodic checks

---

## FAQ

**Does this run on the client or the server?**  
This system is meant to evaluate visibility on the server.

**Can I adjust how often checks happen?**  
Yes. The check interval is configurable so you can balance responsiveness and performance.

**Can it work with different game types?**  
Yes. It supports both 2D and 3D environments, so it can adapt to different Unity projects.

**How do I test visibility behavior?**  
Turn on debug visualization to inspect raycast behavior and tuning results during development.

**What if my networking stack is not Netcode for GameObjects?**  
The system is designed to work with multiple Unity networking solutions, so it can be integrated with the stack used in your project.

**Where should I look if something is not behaving as expected?**  
Start with raycast layers, occlusion masks, team filtering rules, and the server-side update frequency.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
