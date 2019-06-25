---
layout: post
title: Human readable addresses
published: true
author: kingsleh
---

Getting involved with blockchain technology and cryptocurrencies has been really fun. But there is one aspect I continue to struggle with and that is my wallet address. For every blockchain I have a long and complicated wallet address e.g. Neo, Lisk, Bitcoin to name a few.

Obviously I'm not the first person to struggle with this and so on the Ethereum platform there is an smart contract based service called [Ethereum Name Service (ENS)](https://ens.domains/). This allows you to register, buy and sell names in the format `name.eth`. It's essentially a mapping of a name to an Ethereum address so that sending and receiving tokens/coins can use this short human readable name.

Unfortunately with ENS because it's external to the core blockchain each wallet or app needs to be specifically coded to be able to use the name. While there are several popular wallets that support ENS - the majority of exchanges do not. 

But I really like the idea of human readable addresses and it made much more sense to build it into the core blockchain so that no matter where a transaction is being received from the name can always be used instead of the address.

So what does a SushiChain wallet address look like then? Well you guessed it - a long and complicated jumble of letters and numbers which is hard to remember.

It's actually made up of 2 parts:

1. The network type e.g. testnet or mainnet
2. The public key (a 128 bit secure random key)

Then we base64 encode the two parts of data to produce our SushiChain address:

`VDAxNmM1OGVkNmYyNzI2NzcyYjYzODRmMzJmMDkzODhjMTczNWI0NDFjZGM5ZTIz`

I'll probably go into more detail about how our crypto works in a future blog post.

We have recently finished work on our version of ENS. It's called SCARS - SushiChain Address Resolution System. As I mentioned earlier it's built right into the core blockchain. In SCARS we call the name that is mapped to the address a `domain`

So let's take a look at SCARS:

![sushi1](https://raw.githubusercontent.com/sushichain/jekyll-now/gh-pages/images/human-readable-addresses/sushi_scars1.png)

As you can see there are a number of things you can do from the `sushi` command line client.

Registering a domain is currently free but every transaction on SushiChain has a fee. So for each of the available actions there is a small fee. But we want to encourage people to use the SCARS system instead of trying to remember complicated address keys.

A domain has to be alphanumerics followed by `.sc` and must be between 1 and 20 characters in length. So I could choose `kingsleyh.sc` if I didn't mind my address being related to my identity or something more anonymous like `fullmetal.sc`.

You can choose to sell a domain and you can specify the price (in SHARI) that you want for it. And you can decide to cancel the sale if you change your mind before someone else buys it.

Currently you can register as many domains as you like against your address. This may change in the future.

