---
id: maintain-common-validator-logs-explanation
title:  Common Validator Logs Explanation
sidebar_label: Common Validator Logs Explanation
---

> The following information applies to the Polkadot, Kusama, Westend networks Validators. 

This guide will explain some of the common logs you could encounter while running a Validator on the Polkadot network.

## Preliminaries

Running a validator on a live network is a lot of responsibility! You will be accountable for not
only your own stake but also the stake of your current nominators. If you make a mistake and get
slashed, your money and your reputation will be at risk. However, running a validator can also be
very rewarding, knowing that you contribute to the security of a decentralized network while growing
your stash.

# Polkadot and Kusama Common Logs
## Here are some Polkadot, Kusama, and Westend logs and what they mean. ##
Few questions come to mind when troubleshooting the issue

- Are you running the latest version of the code?
 https://github.com/paritytech/polkadot/releases/
- What is the current system utilization?
- What flags are you running with?

## You can review some of the reported Bugs here and report new once https://github.com/paritytech/polkadot/issues

## To see your logs you can run this command
```
sudo journalctl -u polkadot.service -n 1000
```
You can modify the ```1000``` to display fewer or more logs
## Common Log (Life is good)
![image](https://user-images.githubusercontent.com/66147586/125215077-1cf50900-e26f-11eb-891b-e3aab65cb95e.png)

## Block #8302347 has been imported
```
 Imported #8302347 (0x296d…fb2f)
```
## You have 49 peers (in and out connections), the current block is #8302347, and your node finalized block #8302345 Downloading 2.7MiB/s and Uploading ⬆ 1.9MiB/s
```
 Idle (49 peers), best: #8302347 (0x296d…fb2f), finalized #8302345 (0x22e3…877e), ⬇ 2.7MiB/s ⬆ 1.9MiB/s
```
- By default you should have around 50 peers, you can modify it to reduce or increase the number
- Increasing number of peers will cause bigger bandwidth utilization but there is no proof that it will increase era points

## Your node just discovered a new peer 
```
 Discovered new external address for our node: 
/ip4/x.x.63.128/tcp/30333/p2p/12D3KooWDz7FcPsbr8v5pvPngz4GtYWVrzYBsn3CLb5NVEHPBfQa
```
## Reorgs are fine and normal
```
  Reorg on #8302389,0x2813…6e7d to #8302389,0x012f…a2fd, common ancestor #8302388,0x723f…b858
```
## This is what you want to see, your node has authored a block 
```
 Starting consensus session on top of parent 0xcc0d40157526a1447fde0249d054c44e797b5ee8fd3c46b0ef06cacbdcd2b9b1
 Prepared block for proposing at 8302664 [hash: 0x5de0dd21af6f60efe7fd90e750c323868c08573cb432aa741c684200b4864bfc; 
parent_hash: 0xcc0d…b9b1; extrinsics (2): [0x8e13…4d35, 0xc9e6…2eb1]]
```
## Node is syncing, target, best and finalized blocks are displayed 
```
  Syncing  0.3 bps, target=#8303186 (30 peers), best: #8303176 (0xca88…809f), 
finalized #8303175 (0x04ed…4512), ⬇ 49.2kiB/s ⬆ 410.8kiB/s
```
## You will not be seeing this too often, increase the number of Validators in the Active set
```
 new validator set of size 350 has been elected via ElectionCompute::Unsigned for era 905
```
## New epoch 14189 will start in block 0x9c17…9142 
```
 New epoch 14189 launching at block 0x9c17…9142 (block slot 271007079 >= start slot 271007079).
```
## New epoch starts in slot 271007679
```
 Next epoch starts at slot 271007679
```
## Are you running the latest version of the code? Are you sure?
```
 Error importing block 0xbe4cdf08f705a8095a0d860ae6dfd17ef0e4766508c40d5d1a5efd4cbf6ba23d: Err(Other(ClientImport
("Invalid operation in the pending changes tree: Tried to import or finalize node that is an ancestor of a
previously finalized node")))
```
You will see this if your node is running an incorrect version.

# Errors
![image](https://user-images.githubusercontent.com/66147586/125225233-cb0aae00-e283-11eb-865a-b742d7724a82.png)

## Your node was experiencing some issues with ```tokio-runtime-worker``` report this bug
```
Thread 'tokio-runtime-worker' panicked at 'Trying to pin pending state', /usr/local/cargo/git/checkouts/substrate-7e08433d4c370a21/1b758b2/client/state-db/src/noncanonical.rs:527 This is a bug. Please report it at: https://github.com/paritytech/polkadot/issues/new
```
## 
```
Some network error occurred when fetching erasure chunk origin=Public(dcf82a726e45a02a61d0944a21969750772267ca1e
7892c331921d145114032d (Ha3mnqkj...)) err=Network(DialFailure)
```
##
```
Some network error occurred when fetching erasure chunk origin=Public(a8538adafe7f2da1161b7779db0461a4c21464e190
27884a31a5748256dbb64c(GP2NyYRz...)) err=Network(Timeout)
```
## 
```
Importing locally an already known assignment fingerprint=Assignment(0x011fd2b189b6e9ec6c69b72625bc7e9ef7c213d43
c47fd5af523301cce4c4203,0, ValidatorIndex(88))
```
##
```
Got a bad approval from peer peer_id=PeerId("12D3KooWS8CrsBPHzJBL6gu8AqoB83UuNw744pbJ73ZTEGijd5Kc") 
error=Unknown block: 0x435f610ae1bb035bead9a54988108cb56606d1a2d9cbdda28c5dcae69ecc6e80"
```
##
```
panicked at 'Digest item must match that calculated.', /cargo-home/git/checkouts/substrate-7e08433d4c370a21/1d04678/
frame/executive/src/lib.rs:456:13
```
##
```
WARN tokio-runtime-worker parachain::dispute-distribution: error=Runtime(RuntimeRequest(RuntimeApiError("Application(UnknownBlock("State already discarded for BlockId::Hash(0x40c09f3f8c3e1ab11d9f88213847714a1fb701bfebd7a58fe99be45d1d8ad097)"))")))
```
##
```
(offchain call) Error submitting a transaction to the pool: RuntimeApi("Potential long-range attack:
block not in finalized chain.")
```
##

```
Advanced session window for approvals update=Advanced { prev_window_start: 15325, prev_window_end: 15330, new_window_start: 15326, new_window_end: 15331 }
```
## 

```
unsigned transaction validation failed due to Module { index: 37, error: 2, message: Some("PreDispatchWeakSubmission") }
```
##
```
The requester of candidate validation dropped
```
##
```
Importing locally an already known approval fingerprint=Approval(FpHash, 1, ValidatorIndex(2))
```
##
```
fetch_pov_job err=FetchPoV(NetworkError(Network(DialFailure)))
```
##
```
Detected prevote equivocation in the finality worker: Equivocation
```

## 
```
systemd[1]: Started Polkadot Node.
polkadot[15309]: 2021-08-22 13:57:07 Low open file descriptor limit configured for the process. Current value: 4096, recommended value: 10000.
```

##
```
Fetching collation failed due to network error hash=0xd94c9dfda0b98974bfea0eaa56dd0be6afeb93094c35bf111c65669ccc68ba1e
para_id=Id(2007) peer_id=PeerId("12D3KooWMKZKyvxcerX4fWp8ykhVFuYNRKupLApBSckqZGs814k7") err=Network(Timeout)
```
## https://github.com/paritytech/polkadot/blob/c0387bab91c324bb342e2c5de3910ad6d2d1b91b/node/core/candidate-validation/src/lib.rs
```
Failed to validate and make available: Mpsc(SendError { kind: Disconnected })
```

## Polkadot service has been stopped, this could be because you restarted the server, service or node crashed
```
Stopped Polkadot Node.
```
## Polkadot service has been started, this could be because you restarted the server, service or node crashed and was automatically started using servicemd. 
```
Started Polkadot Node.
```
## 
```
Failed to fetch basics from runtime API err=RuntimeApiError("Application(NotInFinalizedChain)")
```
## 
```
Failed to decode transactions list
```
## I'm Online message has been sent by your Validator node, this usually happens in the 2nd half of the Session if your node has not produced a block.
```
[index: 242] Reporting im-online at block: 8785522 (session: 14996): Call::heartbeat(Heartbeat { block_number: 8785522, network_state: OpaqueNetworkState... 
```

##
```
Potential safety failure: reverting finalized block (7714603, 
0x5156dfc5487fd4028293e9c7b99f3472ca4fefe3e103db79f77df53b9ad751bc)
```
## https://github.com/paritytech/polkadot/blob/c0387bab91c324bb342e2c5de3910ad6d2d1b91b/node/network/availability-distribution/src/lib.rs 
```
error=Runtime(RuntimeRequest(RuntimeApiError("Application(NotInFinalizedChain)"))) 
ctx="Error in Requester::update_fetching_heads"
```

## Error after upgrading to 0.9.9 befor 0.9.9-1 was Released
```
error=Runtime(RuntimeRequest(RuntimeApiError("Application(UnknownBlock(\"State already discarded for BlockId::Hash(0x25153021ad82dc150958d1c128da1aa6285475b1bb48b7fe10c9e1e7f8757ea4)\"))")))
```
## https://github.com/paritytech/polkadot/blob/c0387bab91c324bb342e2c5de3910ad6d2d1b91b/node/network/approval-distribution/src/lib.rs
```
Importing locally an already known assignment fingerprint=Assignment
(0xe1a76acab8c5e94b79d6fb8d7c18c774ef8a2f6f2eccb7b1256c12647af41774,0, ValidatorIndex(172))
```
## Some issues connecting to the Telemetry server
```
 Error while dialing /dns/telemetry.polkadot.io/tcp/443/x-parity-wss/%2Fsubmit%2F: Custom { kind: Other, error: Timeout }
```
## https://github.com/paritytech/polkadot/blob/8a6af4412ffc6d327775310c9b4ff527f3345958/node/network/collator-protocol/src/validator_side/mod.rs
```
Trying to insert a pending candidate failed, because there is already one! relay_parent=0xd94c9dfda0b98974bfea0
eaa56dd0be6afeb93094c35bf111c65669ccc68ba1e candidate=0x00b0ec80ec2e47237cd5de2c4ce9ee97028fe543eb5b29256383a664fb6f9682
```
## https://github.com/paritytech/polkadot/blob/f9d71f8c7eb1992efefcba17ed530c1440adb224/node/network/availability-distribution/src/pov_requester/mod.rs
```
fetch_pov_job err=FetchPoV(NetworkError(Network(Timeout)))
```
##
```
(offchain call) Error submitting a transaction to the pool: RuntimeApi("Potential long-range attack: 
block not in finalized chain.")
```
## https://github.com/paritytech/polkadot/blob/c0387bab91c324bb342e2c5de3910ad6d2d1b91b/node/network/approval-distribution/src/lib.rs
```
Got a bad approval from peer peer_id=PeerId("12D3KooWS8CrsBPHzJBL6gu8AqoB83UuNw744pbJ73ZTEGijd5Kc") 
error=Unknown block: 0x435f610ae1bb035bead9a54988108cb56606d1a2d9cbdda28c5dcae69ecc6e80"
```
## https://github.com/paritytech/polkadot/blob/8a6af4412ffc6d327775310c9b4ff527f3345958/node/network/bridge/src/lib.rs
```
Shutting down Network Bridge due to error err=Context("Signal channel is terminated and empty.")
```
##
```
join multicast failed: Address already in use (os error 98)
```
## Well this is where we need to do some troubleshooting
![image](https://user-images.githubusercontent.com/66147586/125232946-833f5300-e292-11eb-8ac6-413c0661904c.png)
