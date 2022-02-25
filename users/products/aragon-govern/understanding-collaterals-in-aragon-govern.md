---
cover: ../../../.gitbook/assets/60a39be473bc185893775da8_govern.png
coverY: 0
---

# Understanding collaterals in Aragon Govern

Aragon Govern relies on the premise that actors will operate in the best interest of the DAO, and that these actors will not schedule transactions that are non-conform to the DAO's agreement.

This said, to provide additional security, all transactions can be challenged before being executed. When a given transaction is challenged, a dispute is created in Aragon Court (or any dispute resolution system that is compliant with ERC-3k), and guardians will be summoned to arbitrate the case.

To make sure that not only this process, but also the process of scheduling transactions in the DAO is not abused, both the transaction creator as the person challenging the transaction needs to provide collaterals that will be used against each other when the dispute is created.&#x20;

If the dispute is ruled in favor of the original transaction creator, the person will get the collateral tokens from the challenger. If the transaction is blocked (e.g. the dispute is ruled in favor of the challenger), then the challenger gets the collateral tokens from the transaction creator.

In summary, collaterals make sure members have skin-in-the-game when interacting within an optimistic governance model and will not try to abuse it.

Collaterals also allow DAO creators to restrict transaction and challenge creation to specific token holders so that only certain individuals who hold a specific token can do it.&#x20;
