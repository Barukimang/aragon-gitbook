---
description: Keeping users informed
---

# The Human readable transactions

{% hint style="success" %}
The Human readable transactions = keeping **users informed.**
{% endhint %}

## How does it work?

A big part of Aragon is user-friendliness, and one of the most unfriendly things in the Ethereum world is transaction data.&#x20;

Examine this screenshot of a transaction in MetaMask:

![UTF8 string in MetaMask](https://hack.aragon.org/docs/assets/metamask.png)

Would you know what this transaction does? Not even a developer could tell. This is why we created **Radspec**.

**Radspec is a secure alternative to Natspec**. Natspec was supposed to be a way to describe transactions from a Natspec _expression_ and some transaction data.

The issue with Natspec, however, is that it is insecure. Any JavaScript can execute in Natspec which opens up a lot of potential attacks, like cross-site scripting, which might successfully phish users.

## How to use Radspec <a href="#how-to-use-radspec" id="how-to-use-radspec"></a>

It's as easy as adding `@notice` to functions in the smart contracts.

```solidity
contract Counter is AragonApp {
    /**
     * @notice Increment the counter by `step`
     */
    function increment(int step) auth(INCREMENT_ROLE) external {
        // ...
    }

    /**
     * @notice Decrement the counter by `step`
     */
    function decrement(int step) auth(DECREMENT_ROLE) external {
        // ...
    }
}
```

These Radspec expressions are **written in comments in your source code**, and they will be grabbed by `aragon` and bundled with your app.

The [Aragon client ](the-aragon-client.md)will display these _with_ the transaction a user is about to perform so that they have a clear understanding of what they're about to sign.

![Screenshot of signer showing Radspec](https://hack.aragon.org/docs/assets/radspec.png)

{% hint style="info" %}
Our Radspec expressions show up while signing a transaction.
{% endhint %}

Obviously, this is a super trivial example as we are not actually evaluating anything but we could instead write something more complex.

## &#x20;<a href="#contributing" id="contributing"></a>

{% hint style="info" %}
✏️ [_<mark style="color:purple;">**Contributing**</mark>_](https://github.com/aragon/hack/edit/master/docs/getting-started.md)_<mark style="color:purple;">****</mark>_
{% endhint %}
