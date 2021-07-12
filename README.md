# DOT_KSM_Logs
## Here are some Polkadot, Kusama, Westend logs and what they mean. ##

## Commen Log
![image](https://user-images.githubusercontent.com/66147586/125215077-1cf50900-e26f-11eb-891b-e3aab65cb95e.png)

## Life is good, Block #8302347 has been imported
```
✨ Imported #8302347 (0x296d…fb2f)
```
## Life is good, you have 49 peers (in and out connections), the current block is #8302347 and your node finalized block #8302345 Downloading 2.7MiB/s and Uploading ⬆ 1.9MiB/s
```
💤 Idle (49 peers), best: #8302347 (0x296d…fb2f), finalized #8302345 (0x22e3…877e), ⬇ 2.7MiB/s ⬆ 1.9MiB/s
```
## Life is good, your node discovered a new peer 
```
🔍 Discovered new external address for our node: 
/ip4/100.107.63.128/tcp/30333/p2p/12D3KooWDz7FcPsbr8v5pvPngz4GtYWVrzYBsn3CLb5NVEHPBfQa
```
## Reorgs are fine and normal
```
♻️  Reorg on #8302389,0x2813…6e7d to #8302389,0x012f…a2fd, common ancestor #8302388,0x723f…b858
```
## 🚀🚀This is what you want to see, your node has authored a block🚀🚀
```
🙌 Starting consensus session on top of parent 0xcc0d40157526a1447fde0249d054c44e797b5ee8fd3c46b0ef06cacbdcd2b9b1
🎁 Prepared block for proposing at 8302664 [hash: 0x5de0dd21af6f60efe7fd90e750c323868c08573cb432aa741c684200b4864bfc; 
parent_hash: 0xcc0d…b9b1; extrinsics (2): [0x8e13…4d35, 0xc9e6…2eb1]]
```
## Node is syncing, target, best and finalized blocks are diplayed 
```
⚙️  Syncing  0.3 bps, target=#8303186 (30 peers), best: #8303176 (0xca88…809f), 
finalized #8303175 (0x04ed…4512), ⬇ 49.2kiB/s ⬆ 410.8kiB/s
```
## New  epoch will start in block 0x9c17…9142 
```
👶 New epoch 14189 launching at block 0x9c17…9142 (block slot 271007079 >= start slot 271007079).
```
## New epoch starts in slot 271007679
```
👶 Next epoch starts at slot 271007679
```
## 
```
💔 Error importing block 0xbe4cdf08f705a8095a0d860ae6dfd17ef0e4766508c40d5d1a5efd4cbf6ba23d: Err(Other(ClientImport
("Invalid operation in the pending changes tree: Tried to import or finalize node that is an ancestor of a
previously finalized node")))
```

# Errors
![image](https://user-images.githubusercontent.com/66147586/125214969-a48e4800-e26e-11eb-9549-f457e4baac67.png)

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
fetch_pov_job err=FetchPoV(NetworkError(Network(Timeout)))
```
##
```
(offchain call) Error submitting a transaction to the pool: RuntimeApi("Potential long-range attack:
block not in finalized chain.")
```
##
```
Fetching collation failed due to network error hash=0xd94c9dfda0b98974bfea0eaa56dd0be6afeb93094c35bf111c65669ccc68ba1e
para_id=Id(2007) peer_id=PeerId("12D3KooWMKZKyvxcerX4fWp8ykhVFuYNRKupLApBSckqZGs814k7") err=Network(Timeout)
```
##
```
Failed to validate and make available: Mpsc(SendError { kind: Disconnected })
```

## Polkadot service has been stopped, this could be because you restarted the server, service or node crashed
```
Stopped Polkadot Node.
```
## Polkadot service has been started
```
Started Polkadot Node.
```
## 
```
Failed to fetch basics from runtime API err=RuntimeApiError("Application(NotInFinalizedChain)")
```
##
```
error=Runtime(RuntimeRequest(RuntimeApiError("Application(NotInFinalizedChain)"))) 
ctx="Error in Requester::update_fetching_heads"
```
##
```
Importing locally an already known assignment fingerprint=Assignment
(0xe1a76acab8c5e94b79d6fb8d7c18c774ef8a2f6f2eccb7b1256c12647af41774,0, ValidatorIndex(172))
```
##
```
Trying to insert a pending candidate failed, because there is already one! relay_parent=0xd94c9dfda0b98974bfea0
eaa56dd0be6afeb93094c35bf111c65669ccc68ba1e candidate=0x00b0ec80ec2e47237cd5de2c4ce9ee97028fe543eb5b29256383a664fb6f9682
```
##
```
fetch_pov_job err=FetchPoV(NetworkError(Network(Timeout)))
```
##
```
Shutting down Network Bridge due to error err=Context("Signal channel is terminated and empty.")
```
##
```
join multicast failed: Address already in use (os error 98)
```
