# query命令

#### 查询账户信息

```
$ cetcli query account -h

Query account balance
Usage:
  cetcli query account [address] [flags]
```

该命令用于查询指定地址的账户信息，例如account id，sequence id和账户余额

**例子**

```
cetcli query account coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m --chain-id=coinexdex
{
  "address": "coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m",
  "coins": [
    {
      "denom": "cet",
      "amount": "99869232"
    },
    {
      "denom": "fxt",
      "amount": "18800000000"
    },
    {
      "denom": "ift",
      "amount": "203016075130448000"
    }
  ],
  "locked_coins": null,
  "frozen_coins": [
    {
      "denom": "cet",
      "amount": "706455003"
    },
    {
      "denom": "ift",
      "amount": "999929376944000"
    }
  ],
  "public_key": {
    "type": "tendermint/PubKeySecp256k1",
    "value": "Akmo+x7erjSZqGjRfo1ofkdiz4mLHyHFvTKJwdfHdVjf"
  },
  "account_number": "17",
  "sequence": "61",
  "memo_required": false
}
```

#### 查询区块信息

```
$ cetcli query  block -h

Get verified data for a the block at given height
Usage:
  cetcli query block [height] [flags]
```

该命令会返回指定高度区块的元信息，例如区块hash，区块时间，区块交易数量等

**例子**

```
cetcli query  block 100  --chain-id=coinexdex
{"block_meta":{"block_id":{"hash":"0184F56E0C546805039C31BAE78318B2735328B347F79E604F8BC150B8E82CF4","parts":{"total":"1","hash":"7607C8B65BF6DA304BD6621E334F83775033F9C5BF048918ED0C108B7BA6A4B9"}},"header":{"version":{"block":"10","app":"0"},"chain_id":"coinexdex","height":"100","time":"2019-11-11T02:06:22.601271731Z","num_txs":"0","total_txs":"0","last_block_id":{"hash":"BB55B8FA890971B128A5F2F576230AC02E3ABA182067818F6921CBE9E3243422","parts":{"total":"1","hash":"31864F31B182424585B74E839CA0E35AC1D5EBE39DEE616E2A3BBCDAA86BE336"}},"last_commit_hash":"7930C6895CCB5225A7C63976A3CC01F26E8DB2B2BAE3458CB4174FE2ABF34659","data_hash":"","validators_hash":"EDE374E8865F83092C3D55B341DF059C2B7043F95701433ECB0EB597E52A055F","next_validators_hash":"EDE374E8865F83092C3D55B341DF059C2B7043F95701433ECB0EB597E52A055F","consensus_hash":"048091BC7DDC283F77BFBF91D73C44DA58C3DF8A9CBC867405D8B7F3DAADA22F","app_hash":"D8FAA41E29A4A985C18874C42B0688AA71B80BDEF75D0B9E56DE5833CAD17EB9","last_results_hash":"","evidence_hash":"","proposer_address":"EEE9E89D623F8C2871F05FEFA0A422474327CF20"}},"block":{"header":{"version":{"block":"10","app":"0"},"chain_id":"coinexdex","height":"100","time":"2019-11-11T02:06:22.601271731Z","num_txs":"0","total_txs":"0","last_block_id":{"hash":"BB55B8FA890971B128A5F2F576230AC02E3ABA182067818F6921CBE9E3243422","parts":{"total":"1","hash":"31864F31B182424585B74E839CA0E35AC1D5EBE39DEE616E2A3BBCDAA86BE336"}},"last_commit_hash":"7930C6895CCB5225A7C63976A3CC01F26E8DB2B2BAE3458CB4174FE2ABF34659","data_hash":"","validators_hash":"EDE374E8865F83092C3D55B341DF059C2B7043F95701433ECB0EB597E52A055F","next_validators_hash":"EDE374E8865F83092C3D55B341DF059C2B7043F95701433ECB0EB597E52A055F","consensus_hash":"048091BC7DDC283F77BFBF91D73C44DA58C3DF8A9CBC867405D8B7F3DAADA22F","app_hash":"D8FAA41E29A4A985C18874C42B0688AA71B80BDEF75D0B9E56DE5833CAD17EB9","last_results_hash":"","evidence_hash":"","proposer_address":"EEE9E89D623F8C2871F05FEFA0A422474327CF20"},"data":{"txs":null},"evidence":{"evidence":null},"last_commit":{"block_id":{"hash":"BB55B8FA890971B128A5F2F576230AC02E3ABA182067818F6921CBE9E3243422","parts":{"total":"1","hash":"31864F31B182424585B74E839CA0E35AC1D5EBE39DEE616E2A3BBCDAA86BE336"}},"precommits":[{"type":2,"height":"99","round":"0","block_id":{"hash":"BB55B8FA890971B128A5F2F576230AC02E3ABA182067818F6921CBE9E3243422","parts":{"total":"1","hash":"31864F31B182424585B74E839CA0E35AC1D5EBE39DEE616E2A3BBCDAA86BE336"}},"timestamp":"2019-11-11T02:06:22.601271731Z","validator_address":"EEE9E89D623F8C2871F05FEFA0A422474327CF20","validator_index":"0","signature":"/xZEGBEYrcona4zph3e0Kdf6xCE1iSBjCeTaRPV//8QW0dDFDu4VRg5t3dxkE3bem2yVDWlY4l+CwZjSL6L3DA=="}]}}}
```

#### 查询交易详情

```
$ cetcli query  tx -h

Query for a transaction by hash in a committed block
Usage:
  cetcli query tx [hash] [flags]
```

该命令用于查询指定hash值的交易详情，例如下面是一笔转账交易。

**例子**

```
cetcli query  tx F9DC0B41F5C714B35A7CF96B8E1075C247EEA7DD8224EDBFEF2BA8985E59D885 --chain-id=coinexdex
height: 513351
txhash: F9DC0B41F5C714B35A7CF96B8E1075C247EEA7DD8224EDBFEF2BA8985E59D885
code: 0
data: ""
rawlog: '[{"msg_index":0,"success":true,"log":"","events":[{"type":"message","attributes":[{"key":"module","value":"bankx"},{"key":"sender","value":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m"},{"key":"action","value":"send"}]},{"type":"transfer","attributes":[{"key":"recipient","value":"coinex1pryd0ue4nfmfns3uscnx7g7lmjukx9hztsj3l8"},{"key":"amount","value":"5364000000000cet"},{"key":"sender","value":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m"}]}]}]'
logs:
- msgindex: 0
  success: true
  log: ""
  events:
  - type: message
    attributes:
    - key: module
      value: bankx
    - key: sender
      value: coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m
    - key: action
      value: send
  - type: transfer
    attributes:
    - key: recipient
      value: coinex1pryd0ue4nfmfns3uscnx7g7lmjukx9hztsj3l8
    - key: amount
      value: 5364000000000cet
    - key: sender
      value: coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m
info: ""
gaswanted: 100000
gasused: 24640
codespace: ""
tx:
  msg:
  - fromaddress: coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m
    toaddress: coinex1pryd0ue4nfmfns3uscnx7g7lmjukx9hztsj3l8
    amount:
    - denom: cet
      amount: "5364000000000"
    unlocktime: 0
  fee:
    amount:
    - denom: cet
      amount: "2000000"
    gas: 100000
  signatures:
  - |
    pubkey: coinexpub1addwnpepqfy637c7m6hrfxdgdrghartg0erk9nuf3v0jr3dax2yur478w4vd7g454ej
    signature: !!binary |
      X5Y2aZZLQJ6EWUCYsXiwxR96fonIgjdp0bgpq98GCs5DzBdEOTK6YbqnT1DVUqsLUSBZ2A
      oOCZH1b69Uhf/mVg==
  memo: V36QDrXiqwVD2KYSnh54Lj
timestamp: "2019-11-26T15:19:38Z"
events:
- type: message
  attributes:
  - key: module
    value: bankx
  - key: sender
    value: coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m
  - key: action
    value: send
- type: transfer
  attributes:
  - key: recipient
    value: coinex1pryd0ue4nfmfns3uscnx7g7lmjukx9hztsj3l8
  - key: amount
    value: 5364000000000cet
  - key: sender
    value: coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m
```

#### 查询某类交易信息

```
$ cetcli query  txs -h

Search for transactions that match the exact given tags where results are paginated.
Example:
$ <appcli> query txs --tags '<tag1>:<value1>&<tag2>:<value2>' --page 1 --limit 30

Usage:
  cetcli query txs [flags]
  
Flags:
  -h, --help           help for txs
      --limit uint32   Query number of transactions results per page returned (default 30)
  -n, --node string    Node to connect to (default "tcp://localhost:26657")
      --page uint32    Query a specific page of paginated results (default 1)
      --tags string    tag:value list of tags that must match
      --trust-node     Trust connected full node (don't verify proofs for responses)  
```

**参数解释**

- `--limit:` 每一页显示的交易数量
- `--page:` 指定查询结果的显示页数
- `--tags:` 指定交易的过滤条件

**例子**

```
cetcli query  txs --tags message.module:bankx --limit=2 --chain-id=coinexdex
{"total_count":"23200","count":"2","page_number":"1","page_total":"11600","limit":"2","txs":[{"height":"780","txhash":"E26ACB4D854DE5609FF3AA16F44B2EF9A46757B069C14723DBD1A2A0903012B3","raw_log":"[{\"msg_index\":0,\"success\":true,\"log\":\"\",\"events\":[{\"type\":\"message\",\"attributes\":[{\"key\":\"sender\",\"value\":\"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn\"},{\"key\":\"module\",\"value\":\"bankx\"},{\"key\":\"sender\",\"value\":\"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn\"},{\"key\":\"action\",\"value\":\"send\"}]},{\"type\":\"transfer\",\"attributes\":[{\"key\":\"recipient\",\"value\":\"coinex17xpfvakm2amg962yls6f84z3kell8c5lm7j9tl\"},{\"key\":\"amount\",\"value\":\"100000000cet\"},{\"key\":\"recipient\",\"value\":\"coinex1ue6tfxm8qlthc43s3rg0fvwakrsfme0x2say3e\"},{\"key\":\"amount\",\"value\":\"999900000000cet\"},{\"key\":\"sender\",\"value\":\"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn\"}]}]}]","logs":[{"msg_index":0,"success":true,"log":"","events":[{"type":"message","attributes":[{"key":"sender","value":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn"},{"key":"module","value":"bankx"},{"key":"sender","value":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn"},{"key":"action","value":"send"}]},{"type":"transfer","attributes":[{"key":"recipient","value":"coinex17xpfvakm2amg962yls6f84z3kell8c5lm7j9tl"},{"key":"amount","value":"100000000cet"},{"key":"recipient","value":"coinex1ue6tfxm8qlthc43s3rg0fvwakrsfme0x2say3e"},{"key":"amount","value":"999900000000cet"},{"key":"sender","value":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn"}]}]}],"gas_wanted":"40000","gas_used":"24140","tx":{"type":"cosmos-sdk/StdTx","value":{"msg":[{"type":"bankx/MsgSend","value":{"from_address":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn","to_address":"coinex1ue6tfxm8qlthc43s3rg0fvwakrsfme0x2say3e","amount":[{"denom":"cet","amount":"1000000000000"}],"unlock_time":"0"}}],"fee":{"amount":[{"denom":"cet","amount":"800000"}],"gas":"40000"},"signatures":[{"pub_key":{"type":"tendermint/PubKeySecp256k1","value":"A39OwQ3ZTDyy/Nt3eH0WDZqdNKhafwCMUSZ8gbXkz6oU"},"signature":"FjefpxLNEN3u1jSvxn1mrRZAixqI1bp89zrghgYflzE249LwIMx3JYVefmbSaiOnM/jZxu25tlHrNEqtxDoUbg=="}],"memo":""}},"timestamp":"2019-11-11T02:29:17Z","events":[{"type":"message","attributes":[{"key":"sender","value":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn"},{"key":"module","value":"bankx"},{"key":"sender","value":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn"},{"key":"action","value":"send"}]},{"type":"transfer","attributes":[{"key":"recipient","value":"coinex17xpfvakm2amg962yls6f84z3kell8c5lm7j9tl"},{"key":"amount","value":"100000000cet"},{"key":"recipient","value":"coinex1ue6tfxm8qlthc43s3rg0fvwakrsfme0x2say3e"},{"key":"amount","value":"999900000000cet"},{"key":"sender","value":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn"}]}]},{"height":"972","txhash":"2628E5C7B343F72A60CB0C5166AB42499D99F259D0D9490823E476FD9322BA38","raw_log":"[{\"msg_index\":0,\"success\":true,\"log\":\"\",\"events\":[{\"type\":\"message\",\"attributes\":[{\"key\":\"module\",\"value\":\"bankx\"},{\"key\":\"sender\",\"value\":\"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn\"},{\"key\":\"action\",\"value\":\"send\"}]},{\"type\":\"transfer\",\"attributes\":[{\"key\":\"recipient\",\"value\":\"coinex1ue6tfxm8qlthc43s3rg0fvwakrsfme0x2say3e\"},{\"key\":\"amount\",\"value\":\"25000000000000000cet\"},{\"key\":\"sender\",\"value\":\"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn\"}]}]}]","logs":[{"msg_index":0,"success":true,"log":"","events":[{"type":"message","attributes":[{"key":"module","value":"bankx"},{"key":"sender","value":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn"},{"key":"action","value":"send"}]},{"type":"transfer","attributes":[{"key":"recipient","value":"coinex1ue6tfxm8qlthc43s3rg0fvwakrsfme0x2say3e"},{"key":"amount","value":"25000000000000000cet"},{"key":"sender","value":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn"}]}]}],"gas_wanted":"40000","gas_used":"24220","tx":{"type":"cosmos-sdk/StdTx","value":{"msg":[{"type":"bankx/MsgSend","value":{"from_address":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn","to_address":"coinex1ue6tfxm8qlthc43s3rg0fvwakrsfme0x2say3e","amount":[{"denom":"cet","amount":"25000000000000000"}],"unlock_time":"0"}}],"fee":{"amount":[{"denom":"cet","amount":"800000"}],"gas":"40000"},"signatures":[{"pub_key":{"type":"tendermint/PubKeySecp256k1","value":"A39OwQ3ZTDyy/Nt3eH0WDZqdNKhafwCMUSZ8gbXkz6oU"},"signature":"LxIHE/e4mvtfn3pV5U1G4CVMlmIYJa3qhQns4x4zHN0LlWafvkhVzNY4TCGGsgGw2gpKHnGnklbKV5Z02Xq/Pg=="}],"memo":""}},"timestamp":"2019-11-11T02:35:45Z","events":[{"type":"message","attributes":[{"key":"module","value":"bankx"},{"key":"sender","value":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn"},{"key":"action","value":"send"}]},{"type":"transfer","attributes":[{"key":"recipient","value":"coinex1ue6tfxm8qlthc43s3rg0fvwakrsfme0x2say3e"},{"key":"amount","value":"25000000000000000cet"},{"key":"sender","value":"coinex1tsw5tnf75r2ln4h2r33wzje4hd3vtautv3fchn"}]}]}]}
```

再举一个查询某地址转账记录的例子

```
cetcli query  txs --tags message.sender:coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m --limit=2 --chain-id=coinexdex
{"total_count":"197","count":"2","page_number":"1","page_total":"99","limit":"2","txs":[{"height":"1640","txhash":"CE1B2A3E97A848ACDACEBB7BACBD943406FDBF6F5AB19FCDD5758477027DE361","raw_log":"[{\"msg_index\":0,\"success\":true,\"log\":\"\",\"events\":[{\"type\":\"message\",\"attributes\":[{\"key\":\"module\",\"value\":\"bankx\"},{\"key\":\"sender\",\"value\":\"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m\"},{\"key\":\"action\",\"value\":\"send\"}]},{\"type\":\"transfer\",\"attributes\":[{\"key\":\"recipient\",\"value\":\"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m\"},{\"key\":\"amount\",\"value\":\"20000000000cet\"},{\"key\":\"sender\",\"value\":\"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m\"}]}]}]","logs":[{"msg_index":0,"success":true,"log":"","events":[{"type":"message","attributes":[{"key":"module","value":"bankx"},{"key":"sender","value":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m"},{"key":"action","value":"send"}]},{"type":"transfer","attributes":[{"key":"recipient","value":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m"},{"key":"amount","value":"20000000000cet"},{"key":"sender","value":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m"}]}]}],"gas_wanted":"60000","gas_used":"24120","tx":{"type":"cosmos-sdk/StdTx","value":{"msg":[{"type":"bankx/MsgSend","value":{"from_address":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m","to_address":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m","amount":[{"denom":"cet","amount":"20000000000"}],"unlock_time":"0"}}],"fee":{"amount":[{"denom":"cet","amount":"1200000"}],"gas":"60000"},"signatures":[{"pub_key":{"type":"tendermint/PubKeySecp256k1","value":"Akmo+x7erjSZqGjRfo1ofkdiz4mLHyHFvTKJwdfHdVjf"},"signature":"pWEfKjj5c5CaC0A6sePuMm50RFIXquDe7sMWo5pNKTZO3PhPoT9DJrAhP3lgZTLcREt2eE1t32gq3ZRdYJoQsQ=="}],"memo":""}},"timestamp":"2019-11-11T02:58:17Z","events":[{"type":"message","attributes":[{"key":"module","value":"bankx"},{"key":"sender","value":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m"},{"key":"action","value":"send"}]},{"type":"transfer","attributes":[{"key":"recipient","value":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m"},{"key":"amount","value":"20000000000cet"},{"key":"sender","value":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m"}]}]},{"height":"1749","txhash":"E73B39E6E03950574A7F52AA58D9DAE806CA60B0323A65E4262E67DB99E4E7BB","raw_log":"[{\"msg_index\":0,\"success\":true,\"log\":\"\",\"events\":[{\"type\":\"create_validator\",\"attributes\":[{\"key\":\"validator\",\"value\":\"coinexvaloper1y6xsfgt9e7l2thrzu8j8mv0ahys34jaap83ql0\"},{\"key\":\"amount\",\"value\":\"500000000000000\"}]},{\"type\":\"message\",\"attributes\":[{\"key\":\"module\",\"value\":\"staking\"},{\"key\":\"sender\",\"value\":\"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m\"},{\"key\":\"action\",\"value\":\"create_validator\"}]}]}]","logs":[{"msg_index":0,"success":true,"log":"","events":[{"type":"create_validator","attributes":[{"key":"validator","value":"coinexvaloper1y6xsfgt9e7l2thrzu8j8mv0ahys34jaap83ql0"},{"key":"amount","value":"500000000000000"}]},{"type":"message","attributes":[{"key":"module","value":"staking"},{"key":"sender","value":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m"},{"key":"action","value":"create_validator"}]}]}],"gas_wanted":"300000","gas_used":"27180","tx":{"type":"cosmos-sdk/StdTx","value":{"msg":[{"type":"cosmos-sdk/MsgCreateValidator","value":{"description":{"moniker":"IFWallet","identity":"5203451C458496F5","website":"","details":""},"commission":{"rate":"0.100000000000000000","max_rate":"0.500000000000000000","max_change_rate":"0.100000000000000000"},"min_self_delegation":"500000000000000","delegator_address":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m","validator_address":"coinexvaloper1y6xsfgt9e7l2thrzu8j8mv0ahys34jaap83ql0","pubkey":"coinexvalconspub1zcjduepqcl2ykhctrdff7uetp9v2pj4hcxu32exhura253xghjldeq7fddeqtsp9pv","value":{"denom":"cet","amount":"500000000000000"}}}],"fee":{"amount":[{"denom":"cet","amount":"6000000"}],"gas":"300000"},"signatures":[{"pub_key":{"type":"tendermint/PubKeySecp256k1","value":"Akmo+x7erjSZqGjRfo1ofkdiz4mLHyHFvTKJwdfHdVjf"},"signature":"E5WQKzoMWDIEFy0hn6B18m8sxEPhc6c9uyYXeC/GfG9yiAEvDuyMmMSaNYhy73JXyA05Az+MNzcZiHQgA6VPNQ=="}],"memo":""}},"timestamp":"2019-11-11T03:01:58Z","events":[{"type":"create_validator","attributes":[{"key":"validator","value":"coinexvaloper1y6xsfgt9e7l2thrzu8j8mv0ahys34jaap83ql0"},{"key":"amount","value":"500000000000000"}]},{"type":"message","attributes":[{"key":"module","value":"staking"},{"key":"sender","value":"coinex1y6xsfgt9e7l2thrzu8j8mv0ahys34jaa6gjg3m"},{"key":"action","value":"create_validator"}]}]}]}
```

这个tags的种类非常多，不建议用户通过此命令过滤交易，请使用区块链浏览器。

