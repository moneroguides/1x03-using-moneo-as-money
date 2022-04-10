# GETTING TO GRIPS WITH MONERO - USING MONERO AS MONEY

## PREREQUISITES

* GPG (Linux)
* Kleopatra / gpg4win (Windows)
* Local Monero Node (optional)

<hr/>

### INTRO

Hello again adventurers. Welcome to the third video in the MoneroGuides video series:  **Using Monero as Money**

In this video we will be setting up a wallet, obtaining some juicy Monero and spending it like cash money

So let's get going!


### CHOOSE YOUR WALLET

According to the good folks at Moneropedia, a [wallet](https://www.getmonero.org/resources/moneropedia/wallet.html) holds the information needed to send and receive Monero privately and securely from the blockchain

As with all software, you've got several great options to choose from. Picking the right wallet depends on several factors, starting with your choice of hardware and operating system. A nice list of available wallets can be found at [GetMonero](https://www.getmonero.org/downloads) website. 

In this video, we'll be using **Feather wallet on Linux**.  Grab the software on their [official site](https://featherwallet.org/download/) or via [Github](https://git.featherwallet.org/feather/feather)

If you've been following this series from the beginning, please download and verify the wallet for your OS now. If you've just joined us and feel confused, please start with the first video in our series: *Importing Public Keys and Verifying Hashes*.


### CONNECTING TO THE MONERO NETWORK

Windows users will be ready to connect right after installing Feather

Linux users will likely need to grant permission for either the appimage or executable as follows:

- Open a terminal window and change directory to the folder containing the file
- Type `sudo chmod +x f`
- *Tab* to complete the line
- Type `./f` 
- *Tab* to complete the line
- Hit *Enter* to run

When Feather starts for the first time you will be greeted by the welcome screen with connection options.  Here is where you will choose the Monero node that your wallet will eventually connect to. 

Ready to get going?  Let's dive right in!

After following all the steps in the last video, you should be able to choose the *Select node manually* option

By default your localhost IP address is filled in, along with the default port for Monero [RPC's](https://monerodocs.org/interacting/monero-wallet-rpc-reference/#rpc)

Since we will be using our wallet software on the same machine as the  node, we can leave everything on the default settings for now

If you are using a different computer on the same network, you will need to select the local IP address attributed to the machine hosting the node. This will commonly start with **192.168** and can be found in your network settings. 

To connect to the Monero daemon, you will need to edit the firewall rules on the machine hosting your node. The default port for RPC's is `18081`.

Follow the instructions from our second video *Setting up your own Node*, for all the steps.  You don't need to edit the firewall rules on your router yet.

If you aren't currently hosting your own node, please select the *Auto connect* option. This will instruct Feather to connect you to any one of its preselected nodes.

After selecting the appropriate connection method click *Next*

### NETWORK PRIVACY OPTIONS

Now we're going to select how Feather will route its network traffic. 

The default settings will tell Feather to use Tor for its functions. However if you are using the *Auto connect option* Feather will initially connect to a node using traditional clearnet methods.

As mentioned in the second video in this series, connecting to the Monero daemon over the clearnet will reveal potentially sensitive information to both:

- the node's host
- ***your Internet Service Provider (ISP)***

The tradeoff for privacy is speed.  Tor network traffic is slower and the initial synchronisation will take a great deal longer over Tor.  That said, the default setting is to use Tor in order to keep your Monero activities and IP address private.

Choose *Configure manually* and then *Route all traffic over Tor*

If you are connecting to your own local node you may use the default settings without any worry. However, selecting *Route all traffic over Tor* can always be used as a fail-safe option. This is what we will be doing here today.

Now that we've configured our network settings it's time to move on to generating our seed phrase. Go ahead and select *Next*.


### GENERATING YOUR SEED PHRASE

To continue we're going to select *Create new wallet* and then click *Next*.

As we hit *Next*, Feather randomly generates a list of 14 words known as a seed phrase. Similarly to the PGP standard, both private keys and public keys have been generated during this time. The seed phrase is an encoded copy of our new private keys. This seed phrase is based on the Bitcoin Improvement Proposal (BIP), which aimed to enable storing private keys in a more user-friendly way.

Opposed to the more common 25 word phrase used for Monero keys, this 14 word format enables the automatic storage of another important piece of information, the **restore height**. 

The restore height is a record of when your key pair was created. This is important for when you want to restore your keys to a new wallet. For more information on the seed scheme used by Feather, please take a look at the [documentation](https://docs.featherwallet.org/guides/seed-scheme).

You can regenerate this phrase as many times as you like and when you're happy you should make a record. We suggest you take the time to write these words down on a piece of paper. Be careful to note the order and make it legible. If you ever lose access to your hardware and have written your seed phrase down incorrectly, your funds may well be lost.

Once you have recorded your seed phrase click *Next*. Feather will offer you the same warning and if you're happy to continue, click *I understand*.

We are now prompted to name our wallet and choose the save location. I'm going to choose the encrypted removable disk I set up earlier. Once again, when we're happy click *Next*.

Now we need to choose a password to encrypt our private key. This should be a strong password regardless of whether someone else has access to our hardware. I'm going to be using the password generator bundled with KeepassXC, a password management program.

Once that's done, select *Create/Open wallet*.


### INTRO TO FEATHER WALLET

Feather is a lightweight client. Unlike the official Monero wallet, it doesn't come packaged with the Monero daemon. It has been built as a feature-rich alternative which can be run from any device, including small USB sticks.

For a full list of its features and a comparison table check out the Feather [documentation](https://docs.featherwallet.org/guides/features). We won't be delving into all the options now, so we urge you to do so after watching this video.

To start with we're going to turn our attention to the tool bar at the bottom of the window. On the right, we can see our current balance and a green circle. 

Click *the green circle*. 

This window shows us the node we are connected to, the synchronisation status and some traffic information. If all is well you should see the phrase **`Synchronised`** and evidence of data traffic, then click *OK* to exit.

Next, let's click the *Settings icon*. Here we can access some of the basic options including: preferred fiat currency, appearance, node list and data paths. I'm going to leave these all alone for now. Once again, we suggest you take a good look through the options. When you're finished making your adjustments, click *OK*.


### ACQUIRING FUNDS

As you can see our current balance is `0`, this means that we don't own any outputs on the Monero blockchain.

Let's change that.

There are two dominant methods for acquiring Monero, they are mining and trading. For the purpose of this video we will be trading fiat money for Monero using a service called [LocalMonero](https://localmonero.co). There are of course many other ways to trade, if you're interested in exploring some of them check out the GetMonero [Merchants](https://www.getmonero.org/community/merchants/) page.

We are going to access LocalMonero using Tor. We encourage you to do the same. If you don't already have the Tor browser on your machine please download it now. Remember, make sure you [verify your downloads](https://support.torproject.org/tbb/how-to-verify-signature/).

We're going to search for local buyers who accept cash via mail or in person. This may not suit everyone, however we want to maintain our anonymity by trading with someone who is not interested in our identity. You will of course need an account before trading, so click on the *Rocket ship icon* to learn how the whole process works.

Before we go any further, we will need a destination address for the other party to transfer funds. To generate an address we need to go back to Feather and click on the **Receive** tab.

At present there are two different types of address used in the Monero ecosystem. Primary addresses, which begin with the number `4` and sub-addresses which begin with the number `8`. These addresses are derived from your keys and cannot be used by anyone else.

It's possible to generate many sub addresses. This is great for increasing anonymity and generally speaking it's good practice to use a different sub-address for each sender. Let's generate a sub-address now using the *Create new address* button.

If we right-click on this new address we have a few options, one of which is *Edit label*. I'm going to select this option and enter: 

`localmonero-`

followed by the user name of the trader whom we will deal with. 

Now when Monero is sent to this address Feather will add **`localmonero-`** to the description, making it simple to identify where the funds have come from. 

This is as far as we go in this video. When you have completed your trade and have funds available in your account, please move onto the next section.


### MONERO TRANSACTIONS

As you can see, we managed to complete our first successful trade. We hope you were able to do the same without trouble.

To continue, let's add a new tab to the toolbar. To do so, select *View* and then *Show Coins*. The *Coins* tab lists all the unspent outputs which are owned by your keys. If we right-click on this output and select *Details* we can get all sorts of interesting information. Here we can see the address it was sent to, its current status, the amount sent and blockchain height.

If we now head over to the *Receive* tab, we can see that the address we created before the trade has now been removed. This is a handy feature built into Feather to prevent address reuse.

Before we go any further, it's best that we outline the basics of a Monero transaction. 

Let's first define the term **owned output**. Described simply, an owned output is a record on the Monero blockchain which attributes your keys with a specified amount of Monero. Owned outputs can have any value, as long as it is less than the total amount of Monero in circulation.

Now that we have this definition, we can more easily understand transactions. Every regular transaction on the Monero blockchain is made up of inputs and outputs. This diagram helps to illustrate that. 

Inputs consist of one or more owned output. As owned outputs have fixed values, any number of them may be used as inputs to meet the required outputs.

For regular transactions there will always be at least three outputs: the amounts to be transferred, a miners fee and a term called **change**.

Change is the remaining Monero after deductions have been made for the specified outputs and miner fee. Even if there is no remainder, there will still be an **output with a value of `0`**. This is to make all transactions on the Monero blockchain indistinguishable.

Monero is a privacy-preserving protocol, which means all of this information is encoded and obfuscated. If you are interested in more details please visit the GetMonero [library](https://www.getmonero.org/library/).

### MAKING A PURCHASE

Now that we have some funds, let's spend them! After all, ***Monero Means Money***.

Today, we're going to be buying a VPN subscription for Mullvad from a [proxystore by dys2p](https://digitalgoods.proxysto.re/). Buying a VPN subscription with Monero is a great idea as not only will your IP address be obfuscated, but also your identity if your choose the right service.

Once again, we'll be accessing this site via the Tor browser.

This proxystore is pretty simple to use. First select your product, then your country, now solve the captcha and select *Order*.

Once your order is ready, select *Pay invoice*. This opens up a new window, which shows the amount due and the address to send it to.

Now that we have these details we can head back to our wallet. Select the *Send* tab and fill in the details. Be sure to double-check the address and amount before selecting *Send* once more.

A new window will now open, let's select *Advanced* and have a look at what's going on. Here we can see the inputs, outputs and fee.

If everything looks good, we can finalise the transaction by clicking *Send* once more.

Once the transaction has been confirmed on the blockchain, the proxystore's web page will update and the voucher code will be made available. The current average block time is around two minutes, so you shouldn't have to wait very long at all.


### TRANSACTION IDs AND PAYMENT CONFIRMATION

You may come across an issue with a vendor where your purchase is not made available. It is in this case which you need to be able to prove that you made the transaction.

The vendor will most likely ask for a **payment ID** and because Monero is a privacy protocol you will also need to provide a **transaction key**, also known as an **outproof signature**.

Feather allows us to generate formatted outproofs rather simply. First navigate to the *History* tab and then right-click on the transaction. Select *Create Tx Proof* and then *Prove payment to an address*.

Next we can select *Get formatted proof*, which will then copy the required text to our clipboard.

We can verify this proof ourselves. Start by selecting *Tools* and then *Verify transaction proof*. We can then paste this information and select *Verify*.

Anyone with access to this transaction proof will be able to see both the receiving address and the amount which was transferred.

### LOCKED FUNDS & ACCOUNT MANAGEMENT

You may have noticed that your balance has been equal to zero for some time after your transaction. There is a good reason for this.

Presently all outputs from a transaction are locked for a total of ten blocks after their initial confirmation. This is built into the protocol and is required to ensure security and stability.

This means that any change you may be owed will be remain unavailable for approximately twenty minutes after your transaction. This is one of the major differences between fiat money and Monero and is something that developers hope to remove.

If you plan to make multiple transactions in quick succession it is advisable to either use the **pay to many function** that can be found under the *Tools* tab or, you generate multiple outputs.

Let's navigate back to the *Coins* tab. If we right-click on the owned output we have the option to *Sweep output*. We can then select *Send to self* and specify the number of outputs. In this case I want to seperate this into 5 outputs, which is equivilent to splitting a €100 note into five €20 notes.

This is one of the only times you would use your primary address and Feather does this automatically. It will now generate the specified number of outputs, with an equal amount of Monero in each.

Upon confirming the transaction you will see the history logged to the wallet file. Once the transaction has been confirmed on the blockchain the outputs will become visible once again in the *Coins* tab.

Another way of achieving this is by creating additional accounts.

If we once again turn our attention to the *bottom toolbar* we will see an icon next to the node status. If we click on this, a new window will open with the **Accounts Management Tool**. You may create as many accounts as you like as these are simply additional sub-addesses which are grouped with a specific label. 

Be warned, names and labels are wallet feature and if you restore your keys to a different wallet this information is not maintained.

### SEEDS AND KEYS

As we have already discovered your seed phrase is an incredibly important thing to keep safe a secure. We also know that Feather is unique to other wallets as it records seed phrases in 14 words.

What if we wanted to restore these keys to a different wallet?

To access the standard 25 word phrase and restore height we need to select *Wallet* from the top toolbar and then *Seed*. Once we've entered the password we will be presented with our seed phrase. All we need to do is select *Show 25 word seed*. If you plan to make these keys available in any other wallet, it would be good to write these down as well.

When you're finished, click *OK*.

Seed phrases are not the only way to restore access to your keys. You can also do it with the keys themselves and interestingly you can provide wallets with limited privileges this way.

To view our keys, once again select *Wallet* and then *Keys*. You will notice that there are 5 keys in total, each of which serves a special function. The ones we're interested in are the **Secret spend key** and **Secret view key**. These keys, together with the primary address are equivalent to the seed phrase.

With just the primary address, restore height and view key, it is possible to create something called a **View Only wallet**. This kind of wallet enbles you and other parties the ability to view the history and current funds attributed to your keys.

This feature exists because unlike protocols which are not private by design, there is no other way to share this information. This is practical for many reasons including the ability to provide financial records and to pay your taxes. 

### CONCLUSION

In this video we have covered just the foundational aspects of using Monero as money and how to interact with Feather.

Nevertheless, we hope you've learnt a lot and will now take the time to expand your knowledge and experience.

Anyway, that's all for this video, thank you for watching and peace be with you privacy fans.
