![btc-hack](https://socialify.git.ci/DavidMGilbert/btc-hack/image?description=0&font=Raleway&forks=1&issues=1&language=1&owner=1&pattern=Circuit%20Board&pulls=1&stargazers=1&theme=Dark)


<h2 align=center>
  <a href="#">
    <img src="https://forthebadge.com/images/badges/built-by-codebabes.svg">
  </a>
  <a href="#">
    <img src="https://forthebadge.com/images/badges/powered-by-coffee.svg">
  </a>
  <a href="#">
    <img src="https://forthebadge.com/images/badges/pretty-risque.svg">
  </a>
  <a href="#">
    <img src="https://forthebadge.com/images/badges/made-with-out-pants.svg">
  </a>
 </h2>

<h2 align=center> ⚠ PLEASE NOTE: This code is only for educational purposes. ⚠ </h2>
<h2 align=center> ⚠ If you do something illegal expect to be held responsible for your own actions. ⚠ </h2>

<h2 align=center> 📑 Introduction </h2>

This program is essentially a brute forcing algorithm. It continuously generates random Bitcoin private keys, converts the private keys into their respective wallet addresses, then checks the balance of the addresses. If a wallet with a balance is found, then the private key, public key and wallet address are saved to the text file `found.txt` on the user's hard drive. The ultimate goal is to randomly find a wallet with a balance out of the 2<sup>160</sup> possible wallets in existence. 

A private key is a secret number that allows Bitcoins to be spent. If a wallet has Bitcoins in it, then the private key will allow a person to control the wallet and spend whatever balance the wallet has. So this program attempts to find Bitcoin private keys that correlate to wallets with positive balances. However, because it is impossible to know which private keys control wallets with money and which private keys control empty wallets, we have to randomly look at every possible private key that exists and hope to find one that has a balance.

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

<h2 align=center> 👨🏻‍💻 How to get started? </h2> 

 Compiling & Use
 --------

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

<h2 align=center> 📝 How to Contribute & To do </h2>  

- [X] Find a faster FREE API with greater allowances. 

<h2 align=center> ✨ Contributors ✨ </h2>
  
  <table>
	<tr>
		<td>
			<a href="https://github.com/DavidMGilbert/btc-hack/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=DavidMGilbert/btc-hack" />
      </a>
		</td>
	</tr>
</table>

Contributions of any kind welcome!

<h1 align=center> Project Admin </h1>
<p align="center">
  <a href="https://www.davidmgilbert.com"><img src="https://avatars.githubusercontent.com/u/118702908?v=4" width=150px height=150px /></a>   

<h1 align=center>Happy Hacking 👨‍💻</h1>



