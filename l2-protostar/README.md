# Important Contract Address
STARKNET_ACCOUNT = 0x33507ff2edf12c12c73d0b6d1d90de9fac12a355de1097ab305249612451919
CONTRACT_ADDR = 0x02882e143918b3742cbb4634217fed3e4f9fb19feb251857388cad5059f3522e
MockStarknetMessaging = 0x5f4E984e3c3Bf84BB27Edb463F65853451492c36
L1L2 = 0xc8EA0c0FB46AddD55Ad325E10217e51238C8dc3f
metamask = 1017334263022290153933902260565188137117688336083

# Deploy Smart Contract
```
starknet-devnet --seed 1234

protostar build
protostar -p devnet declare ./build/l1l2.json --account-address 0x33507ff2edf12c12c73d0b6d1d90de9fac12a355de1097ab305249612451919 --private-key-path ./.pkey --max-fee auto

protostar -p devnet deploy 0x06c9768b03ed4256d6c6e4d2374cda8c51dbf775225a285d9db16b48f1170c40 --account-address 0x33507ff2edf12c12c73d0b6d1d90de9fac12a355de1097ab305249612451919 --private-key-path ./.pkey --max-fee auto
```

# Invoke Smart Contract
```
protostar -p devnet invoke --contract-address 0x02882e143918b3742cbb4634217fed3e4f9fb19feb251857388cad5059f3522e --function "increase_balance" --account-address 0x33507ff2edf12c12c73d0b6d1d90de9fac12a355de1097ab305249612451919 --inputs 1017334263022290153933902260565188137117688336083 100 --max-fee auto --private-key-path ./.pkey

protostar -p devnet call --contract-address 0x02882e143918b3742cbb4634217fed3e4f9fb19feb251857388cad5059f3522e --function "get_balance" --inputs 1017334263022290153933902260565188137117688336083
```

# Send L2 message to L1

```
protostar -p devnet invoke --contract-address 0x02882e143918b3742cbb4634217fed3e4f9fb19feb251857388cad5059f3522e --function "withdraw" --account-address 0x33507ff2edf12c12c73d0b6d1d90de9fac12a355de1097ab305249612451919 --inputs 1017334263022290153933902260565188137117688336083 10 0xc8EA0c0FB46AddD55Ad325E10217e51238C8dc3f --max-fee auto --private-key-path ./.pkey
```