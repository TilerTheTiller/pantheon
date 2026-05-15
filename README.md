<div align="center">
  <h1>PANTHEON</h1>
  <p><strong>Modular GLua admin system for Garry's Mod</strong></p>
  <p>
    <img src="https://img.shields.io/badge/version-2.0.0-1f6feb?style=for-the-badge" alt="Version 2.0.0" />
    <img src="https://img.shields.io/badge/status-archived%20%2F%20unsupported-b91c1c?style=for-the-badge" alt="Archived and unsupported" />
    <img src="https://img.shields.io/badge/platform-Garry%27s%20Mod-15803d?style=for-the-badge" alt="Garry's Mod" />
    <img src="https://img.shields.io/badge/language-GLua-d97706?style=for-the-badge" alt="GLua" />
  </p>
</div>

> [!WARNING]
> PANTHEON is no longer being supported or updated. This repository is being kept online as an archive/reference snapshot of the project.

> [!NOTE]
> This was a personal project I built out of boredom. The code in this repository is free to use, modify, learn from, and repurpose as needed.

## Overview

PANTHEON is a modular admin system for Garry's Mod built around a custom loader, a permission and rank model, a command framework, a custom UI layer, and a growing set of staff/admin plugins.

This README is written as a feature snapshot for the current v2.0.0 update in this repository.

## Architecture Snapshot

<table>
  <thead>
    <tr>
      <th>Area</th>
      <th>What ships in this build</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Bootstrap + loader</td>
      <td>Phase-based startup, dependency-aware core loading, module/plugin loading, and bundled library initialization.</td>
    </tr>
    <tr>
      <td>Bundled libraries</td>
      <td>Loader, netstream, nw, xfn, pon, pon2, PTMySQL helpers, SHA2 helpers, and client cvar helpers.</td>
    </tr>
    <tr>
      <td>UI framework</td>
      <td>Custom colors, components, animations, layout helpers, icons, notifications, theme helpers, and admin-facing menus.</td>
    </tr>
    <tr>
      <td>Command framework</td>
      <td>Builder-pattern commands with aliases, argument definitions, permission flags, and shared parsing helpers.</td>
    </tr>
  </tbody>
</table>

## Feature Set In v2.0.0

### Core systems

<table>
  <thead>
    <tr>
      <th>System</th>
      <th>Included features</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Notifications</td>
      <td>Player and staff notification system across shared, client, and server code.</td>
    </tr>
    <tr>
      <td>Terms</td>
      <td>Centralized terminology/messages used by the admin system.</td>
    </tr>
    <tr>
      <td>Data</td>
      <td>Server-side persistence for admin data, player data, sitroom positions, warnings, bans, and related state.</td>
    </tr>
    <tr>
      <td>Utilities + player meta</td>
      <td>String utilities, general helpers, player lookup helpers, and extra player methods for admin mode, flags, and rank interactions.</td>
    </tr>
    <tr>
      <td>Flags</td>
      <td>Permission flag storage, granting/removal, and runtime permission checks.</td>
    </tr>
    <tr>
      <td>Ranks</td>
      <td>Group/rank definitions, immunity handling, rank setup, and rank-targeting rules.</td>
    </tr>
    <tr>
      <td>Authentication</td>
      <td>Admin authentication flow with login/logout handling and password-backed sessions.</td>
    </tr>
    <tr>
      <td>Commands</td>
      <td>Command registration, parsing, aliases, help text, argument definitions, and permission-bound execution.</td>
    </tr>
    <tr>
      <td>Bans</td>
      <td>Ban creation, removal, persistence, and unban support.</td>
    </tr>
    <tr>
      <td>UI + menu framework</td>
      <td>Client UI shell, reusable UI components, and admin menu support.</td>
    </tr>
    <tr>
      <td>Chatbox</td>
      <td>Custom chatbox support, chat tag configuration, and rank/staff chat presentation.</td>
    </tr>
    <tr>
      <td>Logging</td>
      <td>Centralized event logging for commands, chat, staff actions, and moderation events, with viewer support.</td>
    </tr>
    <tr>
      <td>Warnings</td>
      <td>Shared/server/client warning system with categories, storage, and review support.</td>
    </tr>
    <tr>
      <td>Anti-cheat</td>
      <td>Detection/monitoring backend with supporting commands and log integration.</td>
    </tr>
  </tbody>
</table>

### Staff, moderation, and admin workflow features

<table>
  <thead>
    <tr>
      <th>Plugin / area</th>
      <th>Feature list in this build</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>core.lua</td>
      <td>Kick, ban, unban, set rank, goto, bring, noclip, slay, god, freeze, unfreeze, create rank, update rank, and delete rank tools.</td>
    </tr>
    <tr>
      <td>authentication.lua</td>
      <td>Login, logout, set password, auth status, and force logout commands.</td>
    </tr>
    <tr>
      <td>adminmode.lua</td>
      <td>Admin mode toggle, damage blocking while administrating, physgun immunity targeting checks, physgun freeze/unfreeze on reload, HUD status indicator, and player ESP overlay/settings.</td>
    </tr>
    <tr>
      <td>warns.lua</td>
      <td>Warn, unwarn, check warnings, view warns, and clear warnings.</td>
    </tr>
    <tr>
      <td>flags.lua</td>
      <td>Give flag, remove flag, and list flags.</td>
    </tr>
    <tr>
      <td>reports.lua</td>
      <td>Create reports, report players, claim reports, handle reports, and view active reports through a staff-facing UI/data flow.</td>
    </tr>
    <tr>
      <td>viewstaff.lua</td>
      <td>View online staff and their ranks.</td>
    </tr>
    <tr>
      <td>logs.lua</td>
      <td>Open the client-side logs viewer.</td>
    </tr>
    <tr>
      <td>menu.lua</td>
      <td>Open the admin menu.</td>
    </tr>
    <tr>
      <td>help.lua</td>
      <td>Permission-aware help/command listing.</td>
    </tr>
    <tr>
      <td>adminchat.lua</td>
      <td>Staff-only admin chat channel with report-style fallback/notification behavior.</td>
    </tr>
    <tr>
      <td>sitroom.lua</td>
      <td>Set sitroom positions, delete sitroom positions, list sitrooms, teleport to a sitroom, and bring players into a sitroom.</td>
    </tr>
  </tbody>
</table>

### Communication, player control, and server management

<table>
  <thead>
    <tr>
      <th>Plugin / area</th>
      <th>Feature list in this build</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>chat.lua</td>
      <td>Mute, unmute, gag, ungag, MOTD display, private messaging, server say, and center-screen say commands.</td>
    </tr>
    <tr>
      <td>chatcommands.lua</td>
      <td>Chat mute/unmute, OOC, advert, clear chat, help, time, players list, chat tags, my rank, and test chat commands.</td>
    </tr>
    <tr>
      <td>util.lua</td>
      <td>Cleanup, respawn, set health, set armor, strip weapons, bring, goto, return, freeze, slay, god, and ghost commands.</td>
    </tr>
    <tr>
      <td>utility.lua</td>
      <td>Map display, map restart, map reset, give weapon, exit vehicle, clear decals, stop sound, return, set model, give ammo, scale player, freeze props, and unfreeze props.</td>
    </tr>
    <tr>
      <td>fun.lua</td>
      <td>Slap, HP/armor setting, ignite, extinguish, strip, respawn, cloak, uncloak, jail, unjail, buddha, and unbuddha commands.</td>
    </tr>
  </tbody>
</table>

### Security, world control, and gameplay administration

<table>
  <thead>
    <tr>
      <th>Plugin / area</th>
      <th>Feature list in this build</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>anticheat.lua</td>
      <td>Open anticheat tools, whitelist players, and reset anticheat state.</td>
    </tr>
    <tr>
      <td>limits.lua</td>
      <td>Per-rank limits for effects, NPCs, props, ragdolls, SENTs, SWEPs, and vehicles, plus set-limit and view-limit commands.</td>
    </tr>
    <tr>
      <td>jail.lua</td>
      <td>Dedicated jail/unjail system with configurable jail positions, jail walls, spawn handling, vehicle handling, suicide blocking, and jail-state monitoring.</td>
    </tr>
    <tr>
      <td>gamemaster.lua</td>
      <td>Notarget toggle plus NPC weapon, damage, fire-rate, and health overrides, NPC stat clearing, and NPC status inspection.</td>
    </tr>
    <tr>
      <td>Positioning helpers</td>
      <td>Safe empty-position finding for teleports and controlled player placement near targets.</td>
    </tr>
  </tbody>
</table>

## Project Status

This repository should be treated as archived.

- No more planned support.
- No more planned updates.
- No guarantee of fixes, compatibility changes, or future cleanup.

## Usage

The code here is free to use. If you want to take pieces of it, rewrite it, or use it as a base for your own Garry's Mod admin system, go ahead.

If you want the repository to carry a formal license for redistribution beyond this README notice, add a dedicated LICENSE file later.
