<!-- logo -->
<p align="center">
  <img width='300' src="https://raw.githubusercontent.com/seanjameshan/starknet.js/main/img/logo.svg">
</p>

<!-- tag line -->
<h4 align='center'> Wallet extension <b>ArgentX</b> for StarkNet.</h4>

<!-- primary badges -->
<p align="center">
  <a href="https://github.com/seanjameshan/starknet.js/actions">
    <img src="https://img.shields.io/github/workflow/status/seanjameshan/starknet.js/Release">
  </a>
  <a href="https://www.npmjs.com/package/starknet">
    <img src='https://img.shields.io/npm/v/starknet' />
  </a>
  <a href="https://www.npmjs.com/package/starknet">
    <img src='https://img.shields.io/npm/v/starknet/next' />
  </a>
  <a href="https://bundlephobia.com/package/starknet">
    <img src='https://img.shields.io/bundlephobia/minzip/starknet?color=success&label=size' />
  </a>
  <a href="https://www.npmjs.com/package/starknet">
    <img src='https://img.shields.io/npm/dt/starknet?color=blueviolet' />
  </a>
  <a href="https://github.com/seanjameshan/starknet.js/blob/main/LICENSE/">
    <img src="https://img.shields.io/badge/license-MIT-black">
  </a>
  <a href="https://github.com/seanjameshan/starknet.js/stargazers">
    <img src='https://img.shields.io/github/stars/seanjameshan/starknet.js?color=yellow' />
  </a>
  <a href="https://starkware.co/">
    <img src="https://img.shields.io/badge/powered_by-StarkWare-navy">
  </a>
</p>

⬆️ `TODO`: Change to ArgentX

## ⬇️ Use ArgentX Extension

The easiest way get the ArgentX Extension is from the Chrome Extension Store:

<p align="center">
  <a href="https://developer.chrome.com/docs/extensions/mv3/getstarted/#manifest">
    <img src="packages/get-starknet/src/button-download.svg">
  </a>
</p>

## 🌈 Table of contents

- [⬇️ Use ArgentX Extension](#️-use-argentx-extension)
- [🌈 Table of contents](#-table-of-contents)
- [🌐 Usage with your DApp](#-usage-with-your-dapp)
- [👩🏾‍💻 Development](#-development)
  - [Developing chrome extensions](#developing-chrome-extensions)
- [✏️ Contributing](#️-contributing)
- [❤️ Family and friends](#️-family-and-friends)
- [👨🏼‍🎨 Authors and license](#-authors-and-license)

## 🌐 Usage with your DApp

If you want to use this Starknet Wallet extension with your DApp, the easiest way is to checkout the `@argent/get-starknet` package developed in this repo by running:

```bash
yarn add @argent/get-starknet
```

The package is a light wrapper around [starknet.js](https://github.com/seanjameshan/starknet.js) to interact with the wallet extension. You can then use it like the following:

```javascript
import getStarknet from "@argent/get-starknet"

// check if wallet extension is installed and initialized. Shows a modal prompting the user to download ArgentX otherwise.
const starknet = getStarknet({ showModal: true })
const [userWalletContractAddress] = await starknet.enable() // may throws when no extension is detected

// check if connection was successful
if(starknet.isConnected) {
    // If the extension was installed and successfully connected, you have access to a starknet.js Signer object to do all kind of requests through the users wallet contract.
    starknet.signer.invokeFunction({ ... })
} else {
    // In case the extension wasn't successfully connected you still have access to a starknet.js Provider to read starknet states and sent anonymous transactions
    starknet.provider.callContract( ... )
}
```

Checkout [starknet.js](https://github.com/seanjameshan/starknet.js) to learn more about how to use `Provider` and `Signer`.

## 👩🏾‍💻 Development

To contribute to this repository please read the [contributing guidelines](Contributing.md) first.

To setup the repo on your machine just run:

```bash
yarn      # setup dependencies
yarn dev  # run build process for all packages in watch mode
```

This project contains 3 packages:


| package      | description                                                                       |
| ------------ | --------------------------------------------------------------------------------- |
| extension    | ArgentX extension                                                                 |
| get-starknet | npm module to get started with starknet.js and ArgentX quickly                    |
| playground   | example DApp for testing purposes and example for DApps how to use `get-starknet` |

### Developing chrome extensions

To test changes made to the `extension` package you need to load the local unpacked extension into Chrome. Changes are shown after reopening the extension. Changes to `background.js` are just shown after a complete restart of the Chrome process.

1. Open the Extension Management page by navigating to `chrome://extensions`.
2. Enable Developer Mode by clicking the toggle switch next to **Developer mode**.
3. Click the Load unpacked button and select the extension directory.

![Chrome screenshot of setup](https://wd.imgix.net/image/BhuKGJaIeLNPW9ehns59NfwqKxF2/vOu7iPbaapkALed96rzN.png?auto=format)

[Source](https://developer.chrome.com/docs/extensions/mv3/getstarted/#manifest)

## ✏️ Contributing

Everyone is welcome to contribute. Please take a moment to review the [contributing guidelines](Contributing.md).

## ❤️ Family and friends

Since this project were not possible without [starknet.js](https://github.com/seanjameshan/starknet.js) a big thank you to all [starknet.js contributors](https://github.com/seanjameshan/starknet.js/graphs/contributors) and [@seanjameshan](https://github.com/seanjameshan) for starting it. 

One more thank you to the Starkware Team and Discord.

## 👨🏼‍🎨 Authors and license

[Argent](https://github.com/argentlabs) and [contributors](https://github.com/argentlabs/argent-x/graphs/contributors).

MIT License, see the included [License.md](License.md) file.
