
# !!! NEW !!! BTC-Hack-OFFLINE !!!
Search faster using multi-thrteaded support and an offline database with over 43 Million addresses Updated to 11/13/2022!<br/>
<a href="https://github.com/DavidMGilbert/btc-hack-offline"><<< GET IT HERE >>></a>

# BTC-Hack-v2 - Bitcoin Wallet Hack

An automated bitcoin wallet generator that brute forces random wallet addresses by checking their balance in real-time using an online API.

# Like This Project? Give It A Star or please consider donating!

[![](https://img.shields.io/github/stars/davidmgilbert/btc-hack.svg)](https://github.com/davdmgilbert/btc-hack)

My Bitcoin Wallet Address: 1LKKJE62ygo2c9K2Xc8GxuGwpVDnvyRFRD

# UPDATE!!! BTC-Hack-v2.1 - mnemonic

>TESTED WITH A KNOWN BTC WALLET ADDRESS AND THE TXT FILE OUTPUT AND WIN COUNTER WORK!

[![](https://raw.githubusercontent.com/DavidMGilbert/btc-hack/main/screenshot.PNG)]

I have created a v2.1 of this little script that now includes the ability to search by mnemonic phrase in the GUI.

A pre-compiled windows executable is available for download in the releases section.

The original script as well as the new one are available in this repository.

# Dependencies

<a href="https://www.python.org/downloads/">Python 3.6</a> or higher

btc-hack-2.py requires the  modules listed in the <a href="/requirements.txt">requirements.txt<a/>

# Windows Executable
A Compiled windows executable is available from the releases page that can be run natively without the need to install python or any dependencies.


<a href="https://github.com/DavidMGilbert/btc-hack/releases/tag/btc-hack-v2">-> DOWNLOAD <-<a/>
  
# Installation

```
$ git clone https://github.com/DavidMGilbert/btc-hack.git btc-hack
```

# Quick Start

```
$ python3 btc-hack-v2.py
```

# Proof Of Concept

A private key is a secret number that allows Bitcoins to be spent. If a wallet has Bitcoins in it, then the private key will allow a person to control the wallet and spend whatever balance the wallet has. So this program attempts to find Bitcoin private keys that correlate to wallets with positive balances. However, because it is impossible to know which private keys control wallets with money and which private keys control empty wallets, we have to randomly look at every possible private key that exists and hope to find one that has a balance.

This program is essentially a brute forcing algorithm. It continuously generates random Bitcoin private keys, converts the private keys into their respective wallet addresses, then checks the balance of the addresses. If a wallet with a balance is found, then the private key, public key and wallet address are saved to the text file `found.txt` on the user's hard drive. The ultimate goal is to randomly find a wallet with a balance out of the 2<sup>160</sup> possible wallets in existence. 

# How It Works

Private keys are generated randomly to create a 32 byte hexidecimal string using the cryptographically secure `os.urandom()` function.

The private keys are converted into their respective public keys using the `starkbank-ecdsa` Python module. Then the public keys are converted into their Bitcoin wallet addresses using the `binascii` and `hashlib` standard libraries.

The generated address is queried using an online api, and if it is found that the address has a balance, then the private key, public key and wallet address are saved to the text file `found.txt` on the user's hard drive.

# API FAQ

Currently, the program runs and queries the sochain.com api. As this api allows for upto 300 queries per minute for free, it seemed like a really good choice allowing you to test approximately 18,000 adresses per hour, 432,000 addresses per 24 hours or 3,000,000 addresses per week!

# Expected Output

Every time this program checks the balance of a generated address, it will print the result to the user. If an empty wallet is found, then the wallet address will be printed to the terminal. An example is:

>Address: 1MdwiaF9ge9MRaraFBmy9rHjMXb8BYGnwR
>Private key: 017524c0efc4f4c5b126afff9a21b1660f840b0be39dc8407bc16a3668f5e8f4
>WIF private key: 5Hpvp9gYLDSZDyeiEtSmCrjfpHBzaZQLhiWrhp7Nqm4AoQdVwrB
>Public key: 0421B816FC6F0667C0F9F28DD3900F3C27353839EBEE146BD38A50554536DFD49C061DDDB2954596C1BDDC25C7B07198BED224B2C9872CD40824D669B9EDA936E2
>Balance: 0.0

However, if a wallet with a balance is found, then all necessary information about the wallet will be saved to the text file `found.txt`. An example is:

>Address: 1Kz2CTvjzkZ3p2BQb5x5DX6GEoHX2jFS45<br/>
>Private key: 5A4F3F1CAB44848B2C2C515AE74E9CC487A9982C9DD695810230EA48B1DCEADD<br/>
>WIF private key: 5JW4RCAXDbocFLK9bxqw5cbQwuSn86fpbmz2HhT9nvKMTh68hjm<br/>
>Public key: 04393B30BC950F358326062FF28D194A5B28751C1FF2562C02CA4DFB2A864DE63280CC140D0D540EA1A5711D1E519C842684F42445C41CB501B7EA00361699C320<br/>
>Balance: 0.0001456<br/>

  # TO DO
- [X] Find a faster FREE API with greater allowances. 


<a href="https://github.com/davidmgilbert/btc-hack/issues">Create an issue</a> so I can add more stuff to improve
