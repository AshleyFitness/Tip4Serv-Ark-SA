# Tip4Serv Donation plugin for ARK SA

Create your ARK Survival Ascended shop with [Tip4serv.com](https://tip4serv.com/?ads=github) and monetize your community effectively. This addon connects your ARK Survival Ascended server to your online store, executing commands (group, money, items, etc.) in the server console following each donation.

![Tip4Serv](https://tip4serv.com/img/logo.png)

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Installation](#installation)
4. [Commands](#commands-example)
    - [Broadcast](#broadcast)
    - [Sell Items and Experience](#sell-items-and-experience)
    - [Spawn Items and Dino](#spawn-dino-and-items-with-the-exact-armor-durability-damage)
    - [Give Resources](#give-resources)
    - [Sell Points](#sell-points)
    - [Sell Subscriptions](#sell-permissions-for-subscriptions)
    - [Multiply Quantity](#multiply-quantity)
5. [Comparison: Plugin vs RCON](#comparison-plugin-vs-rcon)
6. [Use the Plugin and RCON Together](#use-the-plugin-and-rcon-together)
7. [Support](#support)

## Introduction

This README provides detailed instructions on how to configure and utilize various commands and plugins for managing donations, item sales, experience points, and subscriptions on your ARK Survival Ascended server.

### HMAC Authentication

Tip4serv ensures secure communication by employing HMAC authentication, a robust method used by financial institutions. For more information, refer to the [HMAC Wikipedia page](https://en.wikipedia.org/wiki/HMAC).

## Prerequisites

- An ARK Survival Ascended server with [ARK Server API](https://gameservershub.com/forums/resources/ark-survival-ascended-serverapi-crossplay-supported.683/) installed if using this Tip4Serv plugin.
- RCON access to the server if using the RCON Tip4Serv connection.
- Installation of [ArkShop](https://gameservershub.com/forums/resources/ark-survival-ascended-arkshop-crossplay-supported.714/) and [Permissions](https://gameservershub.com/forums/resources/ark-survival-ascended-permissions-crossplay-supported.713/) plugins if needed.

## Installation

1. **Create an Account:** Sign up at [Tip4serv.com](https://tip4serv.com/?ads=github).
2. **Add Your Server:** Navigate to [MY SERVERS](https://tip4serv.com/dashboard/my-servers) and add an ARK server.
3. **Choose Connection Method:** Select either the plugin or RCON.
4. **Configure Plugins:** Follow the provided instructions to set up the plugins.

## Commands Example

### Broadcast

Send a public thank you message in the server chat.

**Example:**  
- `ServerChat Thank you {arksa_username} for your {total_paid} {currency} donation`

### Sell Items and Experience

Provide players with items or experience.

**Prerequisites:**  
- The Tip4Serv plugin must be used, as these commands are incompatible with RCON.
- Ensure the plugin is installed on the server where the player will receive their items.
- Check the **"Allow server choice"** option and select **"Run only if player is online"** in the product editor.
  
![Options](https://tip4serv.com/img/tuto/runonlyifplayerisonline2.png)

**Examples:**  
- `GiveItem "Blueprint'/Game/PrimalEarth/CoreBlueprints/Items/Structures/Wooden/PrimalItemStructure_WoodFenceFoundation.PrimalItemStructure_WoodFenceFoundation'" 1 1 false`
- `AddExperience 500000 0 0`

Command generator: [ARK COMMANDS](https://arkids.net/commands)

### Sell points

Add points to a player's account, allowing them to purchase in-game items.

**Prerequisites:**  
- [ArkShop plugin](https://gameservershub.com/forums/resources/ark-survival-ascended-arkshop-crossplay-supported.714/) or [WShop UI mod](https://www.curseforge.com/ark-survival-ascended/mods/wshop-ui) is required.
- This command can be executed via the plugin or RCON.

**Example:**  
- `AddPoints {eosid} 51`

### Spawn Dino and items with the exact armor, durability, damage...

**Prerequisites:**  
- [Enhanced spawner](https://ark-server-api.com/resources/srs-enhanced-spawner.74/) is required.
- These commands can be executed via the plugin or RCON.

**Example:**  
`ES.SpawnItemFor {eosid} "Blueprint'/Game/PrimalEarth/CoreBlueprints/Items/Armor/Saddles/PrimalItemArmor_RexSaddle.PrimalItemArmor_RexSaddle'" "" 5 1 {quantity} 50 500 0 0 0`

`ES.SpawnDinoFor {eosid} "Blueprint'/Moros_Indomitable_Duo/IndominusRex/IndoRaptor/IndoRaptorBlueprints/MoroRaptor_Character_BP.MoroRaptor_Character_BP'" "'" 0 260 0 0 0 0 0 M`

### Give Resources

**Prerequisites:**  
- [Extended RCON](https://ark-server-api.com/resources/extended-rcon.111/) is required.
- These commands can be executed via the plugin or RCON.

**Example:**  
`GiveItemToEOSId {eosid} "Blueprint'/Game/PrimalEarth/CoreBlueprints/Resources/PrimalItemResource_Element.PrimalItemResource_Element'" {quantity} 0 0`

### Sell Permissions for Subscriptions

Add or remove permissions for a player.

**Prerequisites:**  
- [Permissions plugin](https://gameservershub.com/forums/resources/ark-survival-ascended-permissions-crossplay-supported.713/) is necessary.
- Commands can be run using the plugin or RCON.
- For multiple maps, add only one server in your product if all servers connect to the same database.

**Examples:**  
- `Permissions.Add {eosid} VIP`
- `Permissions.Remove {eosid} VIP`

**Procedure:**

1. Go to the [product editor](https://docs.tip4serv.com/store-setup/server-commands).
2. Enable subscriptions.
3. Configure the command to execute after payment.
4. Set up the command to execute when the subscription ends.

![Sub](https://tip4serv.com/img/tuto/tutosubark.png)

### Multiply Quantity

Multiply the quantity chosen by the customer using the following syntax: `{quantity*50}`

**Prerequisites:**  
- You must first enable the **"Allow quantity choice"** option in your product settings. 

**Use this command on Tip4serv if you wish to sell bundles of 200 points:**
- `AddPoints {eosid} {quantity*200}`

**This command will execute in your server console after a purchase if a player buys the product four times:**
- `AddPoints 000263b63d2641b080241ce6463a0754 800`

## Comparison: Plugin vs RCON

- **Plugin:**
  - Ideal for player-specific actions, such as giving items or experience.
  - Requires at least one player to be online for command execution.
  - Commands are executed by the buyer when you select the **"Run only if player is online"** option.
  - If you are using identical commands across all your servers, you can use the same API key for each server and only add one server in the "MY SERVERS" section.

- **RCON:**
  - Ideal for adding points or managing subscriptions.
  - Commands are executed directly by the server and can run even if the server is empty.
  - Self-commands like `GiveItem` or `AddExperience` cannot be used.
  - Only commands compatible with `{eosid}` or `{ue5id}` can be used.
  - You need to connect each server in the "MY SERVERS" section and then link them to your products.

## Support

For any questions or assistance, please refer to the [Documentation](https://docs.tip4serv.com) or [Contact Us](https://tip4serv.com/contact).
