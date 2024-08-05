## Donation plugin for ARK:SA (Tip4Serv)

Create your ARK Survival Ascended store with [Tip4serv.com](https://tip4serv.com/?ads=github) and monetize your community.
This addon connects your ARK Survival Ascended server to your online store and delivers orders (group, money, items...) after each donation by typing commands in the server console.

## HMAC authentication

Tip4serv adds a layer of security using HMAC authentication to communicate. It is a strong authentication method that is used by banks [HMAC WIKI](https://en.wikipedia.org/wiki/HMAC)

## Features

Unlimited game servers & commands

Create subscriptions plan

Commands status tracking

Stock management

Deliver roles & messages on Discord

Easily offer a product to a friend

Create coupon code

Create discount

Add managers for your store

Purchase email and invoice

Sales statistics

Private flow for subscribers

Custom sub-domain

Resend commands

Customize store colors

No ads

## Store available in 15 languages

English, Danish, Dutch, French, German, Hungarian, Italian, Norwegian, Polish, Portuguese, Romanian, Russian, Spanish, Swedish and Turkish.

## Several payment methods

Here are the payment methods you can offer your players: Card, Paypal, Google Pay, Ideal, Giropay, Bancontact, Sofort, Sepa, EPS, BACS, Multibanco, BECS, Przelexy24, BOLETO, OXXO, Afterpay.

## Installation

Open an account on [Tip4serv.com](https://tip4serv.com/?ads=github) and add an ARK:SA server in [MY SERVERS](https://tip4serv.com/dashboard/my-servers)

## Commands example

Here are some commands example you can use in the products configuration: [MY PRODUCTS](https://tip4serv.com/dashboard/my-products).
But you can use all commands of the plugins that you have installed on your server.

***Add points to a player and let them buy the items:***

Required: [ARK Shop plugin](https://gameservershub.com/forums/resources/ark-survival-ascended-arkshop-crossplay-supported.714/)

`AddPoints {eosid} 51`

***Send chat message to all players:***

`ServerChat Thank you {arksa_username} for your {total_paid} {currency} donation`

## Add an Item to a Player's Inventory

**Important:** To use this command, you must utilize the designated plugin and not an RCON connection. Additionally, ensure that **Player must be online** is selected in the [product editor](https://docs.tip4serv.com/store-setup/server-commands#id-2.-product-editor).

`GiveItem "Blueprint'/Game/PrimalEarth/CoreBlueprints/Items/Structures/Wooden/PrimalItemStructure_WoodFenceFoundation.PrimalItemStructure_WoodFenceFoundation'" 1 1 false`

## Quantity multiplier

You can also multiply the quantity choosen by the customer like this: {quantity*50}

Note: You must first activate the **Allow quantity choice** option in your product.

Use this command on Tip4serv if you want to sell bundles of 200 points:

`AddPoints {eosid} {quantity*200}`

This will run in your server console after a purchase if the player buys product 4 times:

`AddPoints 000263b63d2641b080241ce6463a0754 800`

## Using the Plugin with Multiple Maps

We recommend installing the plugin on all your maps and connecting all your servers in [MY SERVERS](https://tip4serv.com/dashboard/my-servers). However, product configuration depends on what you are selling.

***Item Sales***

Configuration: Add all your servers in the [product editor](https://docs.tip4serv.com/store-setup/server-commands#id-2.-product-editor) (your different maps) and check the "Allow server choice" box.

Functionality: The player can choose the map where they want to receive their items. Commands will be executed only if the player is connected to the chosen map.

***Permissions and Points Sales***

Configuration: If you are selling only ranks and points and your maps are connected to the same database, add only your most popular server in your [product editor](https://docs.tip4serv.com/store-setup/server-commands#id-2.-product-editor).

Functionality: Commands will be executed even if the player is not connected to the same map.

***Plugin Limitation***

The plugin requires at least one player to be connected for a command to be executed on a server.

***Using RCON Connection***

Configuration: Simply delete the plugins from your servers and connect them via RCON in [MY SERVERS](https://tip4serv.com/dashboard/my-servers)

Advantage: The delivery system via RCON works similarly to the plugin but can execute commands even if no players are connected to the server.

## Need help?

[Documentation](https://docs.tip4serv.com)

[Contact us](https://tip4serv.com/contact)
