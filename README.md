### Unhacked Challenge :: Schnoodle

[![ci](https://github.com/whitenois3/schnoodle/actions/workflows/test.yml/badge.svg)](https://github.com/whitenois3/schnoodle/actions/workflows/test.yml)
![license](https://img.shields.io/github/license/whitenois3/schnoodle?label=license)
![solidity](https://img.shields.io/badge/solidity-^0.8.0-lightgrey)

`08/29/2022`


#### Schnoodle?

[schnoodle](https://www.schnoodle.finance/) is a dao on ethereum mainnet, governed by the SNOOD token.

After running smoothly for its first ~year, on 6/18, the ETH-SNOOD uniswap pair was drained for over 100 ETH.

- token (proxy): [0xd45740ab9ec920bedbd9bab2e863519e59731941](https://etherscan.io/token/0xd45740ab9ec920bedbd9bab2e863519e59731941)
- token (implementation): [0xeac2a259f3ebb8fd1097aeccaa62e73b6e43d5bf](https://etherscan.io/address/0xeac2a259f3ebb8fd1097aeccaa62e73b6e43d5bf)
- uniswap pair [0x0f6b0960d2569f505126341085ed7f0342b67dae](https://etherscan.io/address/0x0f6b0960d2569f505126341085ed7f0342b67dae)

Review the code in this repo, find the exploit, and recover > 100 ETH.

(hint: the issue is in the token implementation, so focus on `src/SchnoodleV9.sol` and `src/imports/SchnoodleV9Base.sol`. no need to look at the other files)


#### How to play

1. Fork this repo and clone it locally.

2. Create an .env file with an environment variable for ETH_RPC_URL (or add the rpc url directly into the test file).

3. Review the code in the `src/` folder, which contains all the code at the time of the hack. you can explore the state of the contract before the hack using block 14983600. ex: `cast call --rpc-url $ETH_RPC_URL --block 14983600 0xd45740ab9ec920bedbd9bab2e863519e59731941 "getFarmingFund()"`

4. When you find an exploit, code it up in `SchnoodleHack.t.sol`. run the test with `forge test -vvv`. the test will pass if you succeed.

5. Post on twitter for bragging rights and tag [@unhackedctf](http://twitter.com/unhackedctf). no cheating.


#### Breaking Down The Exploit

// TODO

<p align="center">
  <figure width="min-content" align="center">
    <img src="./assets/exploit.png">
    <figcaption><i>Source: <code>src/SchnoodleV9.sol</code>. Created using <a target="_blank" href="https://carbon.now.sh">carbon.now.sh</a></i></figcaption>
  </figure>
</p>


#### Shilling @unhacked

For new weekly challenges and solutions, subscribe to the [unhacked newsletter](https://unhackedctf.substack.com/publish/post/69864558).



