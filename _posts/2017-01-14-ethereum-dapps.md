---
layout: post
title:  "Ethereum Ðapps: What They Are and How To Make One"
date:   2017-01-14
---

Ethereum is a platform for creating decentralized web applications and network-enforced, code-based contracts. It's young right now, but its most ardent advocates boldly proclaim that it will lead the way to a "web 3.0" and provide an alternative to formal legal systems for creating and enforcing organizations and contracts. What I intend to do here is provide some relevant information on what an Ethereum application (aka "Ðapp") is, how it works, and most importantly: how to make one (assumes some experience with node.js and web development).

# A brief overview of Ethereum

Before I go into the details of Ðapps, I want to include an introduction to [Ethereum](https://www.ethereum.org/) and contracts for those not familiar. At the heart of Ethereum is the concept of contracts. Contracts are a set of rules, described in computer code, which can be interacted with by users in the Ethereum network. Users can interact with contracts by invoking public methods defined on the contracts; the methods can receive data from the user and return data back to the user if desired. They can perform all sorts of manipulations on the data that they receive and can permanently store data in "storage" variables defined on the contract, which act in place of databases. In this sense, the Ethereum network can be described as a giant virtual machine, on which the contracts operate as virtual programs. (For those curious, this virtual machine is in fact [Turing Complete](https://en.wikipedia.org/wiki/Turing_completeness).)

This virtual machine is enforced by a *blockchain* (a concept stolen unabashedly from [Bitcoin](https://bitcoin.org/en/)), a public record of every change to the state of this machine. The blockchain is jointly maintained by all members of the Ethereum network (which anyone can join by running the program on their machine), making Ethereum *decentralized*. Thus there is no single point of failure for this network, making it robust against any attempts to compromise it.

# Interacting with contracts

Command line tools are available which allow users to interact with contracts and the Ethereum network via the command line, but of course that is not very accessible to most users. This is where Ethereum client applications (aka "decentralized applications" or "Ðapps") come into play. Ethereum provides a Javascript API called [Web3](https://github.com/ethereum/wiki/wiki/JavaScript-API) which allows web applications to access the Ethereum network, when visited using an enhanced browser which supports the API. Two examples of web3-compatible browsers are [Mist](https://github.com/ethereum/mist) and [Metamask](https://metamask.io/). (Metamask is actually just a Google Chrome extension.)

What this means to general the user is that they can download Mist or add Metamask to Chrome and then use the provided interfaces there to connect to their own Ethereum accounts. Once linked to at least one Ethereum account, the user can navigate to the url of a hosted Ðapp and interact with a contract through a web interface.

In summary, a Ðapp is essentially a glorified web application which can tap into the Ethereum network. Ðapps differ from normal web applications in 2 significant ways:

 1. A Ðapp interacts with the *Ethereum network* rather than a server.
 2. A Ðapp must be browsed by an enhanced web browser, as standard browsers do not provide access to the Ethereum network.

![Traditional Web Apps vs Web3 Ðapps](/blog/assets/images/traditional-web-apps-vs-web3-dapps.png)

# A word on the significance and limitations of contracts

It's worth noting at this point that contracts have an interesting property: they cannot be modified. This means that any mistakes made in the contract are permanent; the only way to fix them is to deploy a brand new contract with the fixes. This is certainly an inconvenience, but it also adds an important property to the contracts: it makes them binding. Because the code cannot be modified, the rules of the contract are strictly enforced by the Ethereum network itself. Ethereum proponents suggest that this can be used to create "autonomous organizations" which use Ethereum contracts to enforce rules and "smart contracts" which can be used to enforce payoffs for a bet.

All of this is certainly possible from a technical perspective. Making contracts useful in the real world, however, is more difficult. This is because contracts are just pieces of code, which can only access data within the Ethereum network. Ethereum on its own does not access data from the outside world, and certainly does not possess the capability to interpret that data in any meaningful way (such as verifying the result of a sports game and executing payoffs to the winners of a bet based on that result). Real world data can be fed into the network, but the contracts themselves need to handle all the complexity of validating and interpreting the data, or rely on an external mechanism to do so. This turns out to be a difficult problem, one which requires an entirely separate mechanism to be solved. I will not discuss this problem any further here as my knowledge of it is quite limited, but I did want to mention it.

# Let's make one!

Enough idle talk. Let's build a Ðapp.

Note that familiarity with [node.js](https://nodejs.org/en/) and some web development experience is assumed here. I'm also assuming you're developing on OSX or Linux.

Allow me to introduce some things which we'll be using.

- [Truffle](http://truffleframework.com/): Truffle is a development framework for building Ðapps which provides some nice functionality, such as management of contract deployment, abstractions for interacting with contracts, and (my personal favorite feature) testing support for contracts.

- [Solidity](https://solidity.readthedocs.io/en/develop/index.html): Solidity is actually a programming language. It is a language designed specifically for Ethereum contracts, and as such compiles to byte code which can be deployed directly to the Ethereum network. Solidity is the language of choice for most people writing Ethereum contracts and is the language supported by Truffle.

- [testrpc](https://github.com/ethereumjs/testrpc): Testrpc is a node.js module that provides a fake Ethereum network which can be run locally. This is useless for production, but very handy for development. You can deploy your contracts to testrpc and interact with them as if they were deployed to Ethereum. It's a nice sandbox.

- [Metamask](https://metamask.io/): As mentioned previously, Metamask is just a Chrome extension which allows you to browse a Ðapp. I had no luck with Mist when developing locally (possibly an incompatibility with testrpc), but Metamask worked like a charm. I recommend using Metamask.

### 1. Install testrpc

The first thing you'll want to do is install testrpc. Although I prefer to install npm packages locally, the simplest way to get started is to install it globally: `npm install -g ethereumjs-testrpc`. Note that testrpc requires node version 6.9.1 or greater. I personally use nvm to easily switch between node versions.

### 2. Install truffle

Again, the simplest way to get Truffle is to install it as a global npm package: `npm install -g truffle`.

### 3. Create your project directory

Create a folder for your project, `cd` into it, and then run 2 commands:
- `truffle init`
- `mkdir build && mkdir build/contracts` (creates missing directory needed for builds)

This will create a basic folder structure for your project and initialize it as a bare-bones demo application.

### 4. Try running the demo application

Try running Metacoin, the demo application. Run the following commands:

- `testrpc` (in a separate terminal) - Start the fake Ethereum network. It will run on port 8545. Make sure you're running node v6.9.1 or greater, or this won't work.
- `truffle migrate` (in your project root directory) - Compiles and deploys your contract to testrpc (which must be running).
- `truffle serve` - Serves your web frontend.

Then setup Metamask:
- Install the [Chrome extension](https://metamask.io/).
- Unlock your vault in Metamask. You can do this by copying the mnemonic that should have been displayed in the terminal after booting testrpc. It will look something like this: `february range tired caught talk ripple shrimp interest across exist blur organ`. Click "Restore existing vault" in Metamask and paste the mnemonic. You can set the password to whatever you like.
- Switch to the network `localhost 8545` in Metamask (at the time of this writing, the current network is displayed at the top left of the main screen in Metamask).

If all goes well, you should be able to navigate to `http://localhost:8080` in Chrome and interact with the trivial Metacoin app. Try sending some coin to an address. (You can look at the output from when you started testrpc to get a list of addresses that were generated.)

### 5. Make it your own

That was easy enough, right? Now try implementing your own idea. It can be stupid simple and trivial. Here are the steps you'll probably want to take:

 - Write the contract in Solidity. The [Solidity Browser](https://ethereum.github.io/browser-solidity/#version=soljson-v0.4.8+commit.60cc1668.js) is a nice tool for manually testing out your contracts as you write them. For formal automated tests, take a look at the tests in your demo project. Automated tests are wonderful and Truffle provides testing out of the box. I highly recommend setting aside time to build at least 1 or 2 tests for your contract.

 - Once you have the contract written and tested, you can proceed to create your frontend. Build it however you like: if you like building everything from scratch, do that. If you like using UI frameworks like Bootstrap, go for it. If you like Javascript frameworks such as React, that works too. Note that if you're going to use React (or some other framework that relies on compilation), you'll need to integrate the build process for the framework with the Truffle build process. Thankfully, Truffle supports doing this with Webpack. There is a helpful tutorial [here](http://truffleframework.com/tutorials/bundling-with-webpack).

 If you would like to see another example, you are welcome to take a look at my first Ðapp project: <https://github.com/tyleryasaka/EtherCred>.

 I went beyond the boilerplate example in that project, so it might be useful as an example of a more complex use of Truffle. Some of the things I did include:
 - Using a more complex file structure
 - Using a CSS framework
 - Using [React](https://facebook.github.io/react/) as a Javascript framework
 - Integrating [Webpack](https://webpack.github.io/) for a customized build
 - Integrating my own Javascript tests (using [Mocha](https://mochajs.org/) and [Chai](http://chaijs.com/)) with the Truffle tests
 - Creating an external script which seeds the test network with some sample data for development

# Things to think about

- How does the blockchain really work? How robust is it? What would it take to bring it down?
- How can we bridge the gap between Ethereum and the real world in a way that is resistant to fraud?
- What is the future of the decentralized web? Will it take off? Could "smart contracts" eventually replace traditional legal contracts entirely?
