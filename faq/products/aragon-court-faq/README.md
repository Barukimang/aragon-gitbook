---
cover: ../../../.gitbook/assets/05.png
coverY: 0
---

# Aragon Court FAQ

## <mark style="color:blue;">****</mark>





## <mark style="color:blue;">**Voting**</mark>

###

### What happens if there is a tie?

In case of a tie the highest priority option will be chosen. Refuse to vote will always be the highest priority. On top of that, organizations subscribed to the Court can set up their own priority. Everything else works the same. So, for instance, given a priority of Block > Allow, if in the second round 1 guardians refuses to vote, 4 vote Block and 4 vote Allow, the final outcome (for that round) will be Block. If there are no appeals in that round, then Block is the final ruling and the 4 guardians that voted Block will be rewarded and the rest will be slashed.

### What does "Refuse to vote" mean? What happens if it's the most voted option?

This is an option guardians can choose if they think that the arguments are not complete or coherent enough to make a decision or they think that the dispute doesn't belong in the Court (in the future there may be different specialized Courts). "Refuse to vote" works like any other option: if it's the most voted option, guardians who voted for it get rewards, all the rest get slashed.

### Another guardians tried to collude and leaked his secret password. Can I punish this guardian for attempting to collude?

Yes you can, and you should! There are instructions for what to do in this situation [here](https://help.aragon.org/article/43-dispute-lifecycle#leak).

### What's the penalty for leaked votes?

It's the same as for guardians on the losing side of a final ruling. When a cast vote is leaked it's overwritten to "leaked" instead of the original outcome chosen by the guardians, so it can never be on the winning side, even if their original cast vote would have been on the winning side.

## <mark style="color:blue;">**Governance**</mark>

### Which parameters of Court can be changed? How?

*   Almost all parameters, except for the term duration, period duration, and Court start time can be changed. In particular:

    *   Controller contract:

        * Court parameters:
        *
          * Juror fees
          * Draft fees
          * Settlement fees
          * Argument submission period
          * Commit period
          * Reveal period
          * Appeal period
          * Appeal confirm period
          * Penalty percentage of min active balance to be slashed for losing guardians
          * Final round fees reduction percentage
          * First round guardians number
          * Factor used to increase guardians number in each appeal
          * Number of regular rounds (before final round with all guardians is triggered)
          * Number of terms that a coherent guardians in a final round is disallowed to withdraw (to discourage 51% attacks)
          * Multiple of dispute fees required to appeal a preliminary ruling
          * Multiple of dispute fees required to confirm appeal
          * Minimum amount of guardian tokens that can be activated



        * Governor addresses:
          * Modules governor
          * Funds governor
          * Configuration governor



        * Eject governor addresses i.e. remove without replacing:
          * Eject Funds governor
          * Eject Modules governor



        * Module addresses:
          * Dispute Manager
          * Jurors Registry
          * Voting
          * Treasury
          * Subscriptions
          * Set addresses for new modules



    * Dispute Manager module:
      * Controller address (can only change by deploying a new Dispute Manager module)
      * Number of skipped disputes (can only change by deploying a new Dispute Manager module)
      * Maximum guardians per draft batch (relevant in case a draft is so large it requires multiple transactions or batches)



    * Jurors Registry module:
      * Controller address (can only change by deploying a new Jurors Registry module)
      * Jurors token contract address (can only change by deploying a new Jurors Registry module)
      * Total active balance limit



    * Voting module:
      * Controller address (can only change by deploying a new Voting module)



    * Treasury module:
      * Controller address (can only change by deploying a new Treasury module)



    * Subscriptions module
      * Controller address (can only change by deploying a new Subscriptions module)
      * Period duration (can only change by deploying a new Subscriptions module)
      * Subscriptions fee token
      * Subscriptions fee amount
      * Number of pre-payment periods
      * Number of resume pre-paid periods
      * Governor share %
      * Late payment penalty %



* Only the Aragon Network DAO can change them, through a vote. Currently the Aragon Network DAO is composed of [five council members](https://blog.aragon.one/aragon-network-deploy/#governor-council). It is planned for [control to be transitioned to ANT holders](https://blog.aragon.org/evolving-aragon-network-governance/).

### Do parameter changes affect ongoing disputes?

No, a dispute gets its parameters when it's created and keeps them during the whole life-cycle. So if for instance while a dispute is being adjudicated in the first round the voting period is reduced from 2 days to 1, the dispute will still have a voting period of 2 days all the way through to the final ruling.

## <mark style="color:purple;">**Technical**</mark>

### Where is the Court "hosted"?

Aragon Court is a smart contract system deployed to the [Ethereum](https://ethereum.org) mainnet. The Court Dashboard at [court.aragon.org](https://court.aragon.org) is hosted by Aragon.

### Where can I find the source code and technical documentation for Aragon Court?

The Aragon Court smart contract source code and technical documentation can be found in the [protocol](https://github.com/aragon/protocol) repo on GitHub. The Aragon Court Dashboard source code can similarly be found in the [court-dashboard](https://github.com/aragon/protocol-dashboard) repo.

## <mark style="color:purple;">ANJ conversion</mark>

### **What is the minimum number of $ANJ I need to participate in the 0.044 conversion?**

2400

### **What date will the lock-up period end?**

The 5th of October, 2021.

### **When will the contracts for the conversion be available?**

These are currently being worked on and will be available by July 2021.

### **If I have not staked my $ANJ, do I still get the lockup period price?**

When you convert your $ANJ, the resulting $ANT is automatically staked into Aragon Court v2 and locked until the 5th of October. If you have $ANJ staked in the Aragon Court v1, you will first need to [unstake it](https://v1.court.aragon.org) and send it to your wallet before you can do the conversion.

### **Will I get the 0.044 conversion if I convert after September 5th?**

No, to get the 0.044 staked price you will need to have staked your $ANJ before 23:59 on September the 4th (UTC).

### **How much will it cost to be a Guardian in Aragon Court with $ANT?**

You will have to stake 100 $ANT to become an Aragon Court Guardian.
