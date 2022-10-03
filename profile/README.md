# bridging web2 to web3 🧀

#### 🌐 [Website](https://www.burrata.xyz)    📚 [Documentation](https://docs.burrata.xyz)    💬 [Community](https://t.me/+vvN1naUaBbZlMDgx)
#### 📝 [Changelog](https://docs.burrata.xyz/changelog)    🛣 [Roadmap](https://github.com/orgs/burrata-labs/projects/3)

[![](https://raw.githubusercontent.com/burrata-labs/.github/main/assets/gh-banner.png)](https://github.com/orgs/burrata-labs/)

---
[burrata’s](https://www.burrata.xyz) integration layers helps web3 developers consume private data from web2 systems while maintaining user privacy and control.


## Get started

Developer-first tooling makes creating and verifying on-chain credentials a breeze.

1. Sign up for [early access](https://www.burrata.xyz)

2. Install NPM packages

```js
npm i --save @burrata/sdk
npm i --save @burrata/contracts
```

3. Setup contracts and dApp

<details>
<summary><code>Solidity</code></summary>

```solidity
import "@burrata/contracts/deployment/testnet.sol";

function your_function(bytes calldata burrataData) {
  BurrataClaims.check(
    keccak256("soulnoun.cip"),
    burrataData
  );
}
```
</details>

<details>
<summary><code>Javascript</code></summary>

```js
import { initialize as burrataInit } from '@burrata/sdk.ethers';
import { useState, useCallback } from 'react';

const BURRATA_ENV = process.env.REACT_APP_BURRATA_ENV;

export const useBurrata = () => {
    const [connected, setConnected] = useState(false);

    const connectBurrata: (account: string, signer: any) => Promise<any> = useCallback(
    async (account: string, signer: any) => {
        try {
        const res = await burrataInit({
            account,
            provider: signer.provider,
            info: {
            name: 'SoulNoun',
            logoUrl: 'https://openseauserdata.com/files/605b971d4feefc10a91ce4d1f0cfcd8f.svg',
            },
            environment: BURRATA_ENV,
        });

        setConnected(true);
        return res;
        } catch (error) {
        return error;
        }
    },
    [],
    );

    return [connected, connectBurrata];
};
```

</details>

<br/>

> Read [documentation](https://docs.burrata.xyz) to learn more.

<br/>

## Integrations and use cases

burrata supports various use cases through an integrations model. The following integrations are provided out of box:

1. Identity Verification:
    - [Stripe Identity](https://docs.burrata.xyz)
2. eSignature:
    - [PandaDoc](https://docs.burrata.xyz)
3.  Financial History:
    - [Stripe Financial Connections](https://github.com/orgs/burrata-labs/projects/3/views/1)
    - [Plaid](https://github.com/orgs/burrata-labs/projects/3/views/1)
4. Know Your Customer (KYC):
    - [Persona](https://docs.burrata.xyz)
5. Accredited Investor:
    - [Verify Investor](https://docs.burrata.xyz)
6. Know Your Business (KYB):
    - [Middesk](https://github.com/orgs/burrata-labs/projects/3/views/1)
    - [Persona](https://github.com/orgs/burrata-labs/projects/3/views/1)
7. Employment History:
    - [Truework](https://github.com/orgs/burrata-labs/projects/3/views/1)

Find something missing? Developers can also [`build their own`](https://github.com/orgs/burrata-labs/projects/3/views/1) integrations.


## Get involved

> 👉 Note: By interacting with this organization or community you agree to abide by our [code of conduct](https://github.com/burrata-labs/.github/blob/main/code-of-conduct.md).

* for questions, see [support](https://github.com/burrata-labs/.github/blob/main/support.md)
* to help, see [contribute](https://github.com/burrata-labs/.github/blob/main/contributing.md)
* to report bugs and feature reports, [open an issue]()
* for urgent issues, reach out through [developer community](https://t.me/+vvN1naUaBbZlMDgx)

<br/>

 🌐 [Website](https://www.burrata.xyz)    📚 [Documentation](https://docs.burrata.xyz)    💬 [Community](https://t.me/+vvN1naUaBbZlMDgx)    📝 [Changelog](https://docs.burrata.xyz/changelog)    🛣 [Roadmap](https://github.com/orgs/burrata-labs/projects/3)