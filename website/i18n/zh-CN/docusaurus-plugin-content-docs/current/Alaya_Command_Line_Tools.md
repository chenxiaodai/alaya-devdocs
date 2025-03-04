---
id: Command_Line_Tools
title: Alaya命令行工具
sidebar_label: Alaya命令行工具
---

## Alaya命令行参数说明 

```conf
NAME:
   alaya - the alaya-go command line interface

   Copyright 2019 The Alaya-Go Authors

USAGE:
   alaya [options] command [command options] [arguments...]

VERSION:
   0.16.1-unstable

COMMANDS:
   account           Manage accounts
   attach            Start an interactive JavaScript environment (connect to node)
   console           Start an interactive JavaScript environment
   copydb            Create a local chain from a target chaindata folder
   dump              Dump a specific block from storage
   dumpconfig        Show configuration values
   export-preimages  Export the preimage database into an RLP stream
   import-preimages  Import the preimage database from an RLP stream
   init              Bootstrap and initialize a new genesis block
   inspect           Inspect the storage size for each type of data in the database
   js                Execute the specified JavaScript files
   license           Display license information
   removedb          Remove blockchain and state databases
   version           Print version numbers
   help, h           Shows a list of commands or help for one command

ALAYA OPTIONS:
  --config value                     TOML configuration file
  --datadir "/home/chenglin/.alaya"  Data directory for the databases and keystore
  --datadir.ancient                  Data directory for ancient chain segments (default = inside chaindata)
  --keystore                         Directory for the keystore (default = inside the datadir)
  --nousb                            Disables monitoring for and managing USB hardware wallets
  --networkid value                  Network identifier (integer, 1=Frontier, 2=Morden (disused), 3=Ropsten, 4=Rinkeby) (default: 1)
  --alaya                            alaya network: pre-configured alaya network
  --syncmode "full"                  Blockchain sync mode ("fast", "full", or "light")
  --identity value                   Custom node name
  --lightserv value                  Maximum percentage of time allowed for serving LES requests (0-90) (default: 0)
  --lightpeers value                 Maximum number of LES client peers (default: 100)
  --lightkdf                         Reduce key-derivation RAM & CPU usage at some expense of KDF strength

DEVELOPER CHAIN OPTIONS:
  --dev.period value  Block period to use in developer mode (0 = mine only if transaction pending) (default: 0)

TRANSACTION POOL OPTIONS:
  --txpool.locals value         Comma separated accounts to treat as locals (no flush, priority inclusion)
  --txpool.nolocals             Disables price exemptions for locally submitted transactions
  --txpool.journal value        Disk journal for local transaction to survive node restarts (default: "transactions.rlp")
  --txpool.rejournal value      Time interval to regenerate the local transaction journal (default: 1h0m0s)
  --txpool.pricebump value      Price bump percentage to replace an already existing transaction (default: 10)
  --txpool.accountslots value   Minimum number of executable transaction slots guaranteed per account (default: 16)
  --txpool.globalslots value    Maximum number of executable transaction slots for all accounts (default: 16384)
  --txpool.accountqueue value   Maximum number of non-executable transaction slots permitted per account (default: 64)
  --txpool.globalqueue value    Maximum number of non-executable transaction slots for all accounts (default: 4096)
  --txpool.globaltxcount value  Maximum number of transactions for package (default: 3000)
  --txpool.lifetime value       Maximum amount of time non-executable transaction are queued (default: 3h0m0s)
  --txpool.cacheSize value      After receiving the specified number of transactions from the remote, move the transactions in the queen to pending (default: 0)

PERFORMANCE TUNING OPTIONS:
  --cache value           Megabytes of memory allocated to internal caching (default: 1024)
  --cache.database value  Percentage of cache memory allowance to use for database io (default: 75)
  --cache.gc value        Percentage of cache memory allowance to use for trie pruning (default = 25% full mode, 0% archive mode) (default: 25)
  --cache.triedb value    Megabytes of memory allocated to triedb internal caching (default: 512)

ACCOUNT OPTIONS:
  --unlock value           Comma separated list of accounts to unlock
  --password value         Password file to use for non-interactive password input
  --allow-insecure-unlock  Allow insecure account unlocking when account-related RPCs are exposed by http

API AND CONSOLE OPTIONS:
  --rpc                  Enable the HTTP-RPC server
  --rpcaddr value        HTTP-RPC server listening interface (default: "localhost")
  --rpcport value        HTTP-RPC server listening port (default: 6789)
  --rpcapi value         API's offered over the HTTP-RPC interface
  --rpc.gascap value     Sets a cap on gas that can be used in eth_call/estimateGas (default: 0)
  --ws                   Enable the WS-RPC server
  --wsaddr value         WS-RPC server listening interface (default: "localhost")
  --wsport value         WS-RPC server listening port (default: 6790)
  --wsapi value          API's offered over the WS-RPC interface
  --wsorigins value      Origins from which to accept websockets requests
  --ipcdisable           Disable the IPC-RPC server
  --ipcpath              Filename for IPC socket/pipe within the datadir (explicit paths escape it)
  --rpccorsdomain value  Comma separated list of domains from which to accept cross origin requests (browser enforced)
  --rpcvhosts value      Comma separated list of virtual hostnames from which to accept requests (server enforced). Accepts '*' wildcard. (default: "localhost")
  --jspath loadScript    JavaScript root path for loadScript (default: ".")
  --exec value           Execute JavaScript statement
  --preload value        Comma separated list of JavaScript files to preload into the console

NETWORKING OPTIONS:
  --bootnodes value          Comma separated enode URLs for P2P discovery bootstrap (set v4+v5 instead for light servers)
  --bootnodesv4 value        Comma separated enode URLs for P2P v4 discovery bootstrap (light server, full nodes)
  --port value               Network listening port (default: 16789)
  --maxpeers value           Maximum number of network peers (network disabled if set to 0) (default: 60)
  --maxconsensuspeers value  Maximum number of network consensus peers (network disabled if set to 0) (default: 40)
  --maxpendpeers value       Maximum number of pending connection attempts (defaults used if set to 0) (default: 0)
  --nat value                NAT port mapping mechanism (any|none|upnp|pmp|extip:<IP>) (default: "any")
  --nodiscover               Disables the peer discovery mechanism (manual peer addition)
  --netrestrict value        Restricts network communication to the given IP networks (CIDR masks)
  --nodekey value            P2P node key file
  --nodekeyhex value         P2P node key as hex (for testing)

MINER OPTIONS:
  --miner.gasprice "1000000000"  Minimum gas price for mining a transaction
  --miner.gastarget value        Target gas floor for mined blocks (default: 9424776)

GAS PRICE ORACLE OPTIONS:
  --gpoblocks value      Number of recent blocks to check for gas prices (default: 20)
  --gpopercentile value  Suggested gas price is the given percentile of a set of recent transaction gas prices (default: 60)

LOGGING AND DEBUGGING OPTIONS:
  --nocompaction            Disables db compaction after import
  --verbosity value         Logging verbosity: 0=silent, 1=error, 2=warn, 3=info, 4=debug, 5=detail (default: 3)
  --vmodule value           Per-module verbosity: comma-separated list of <pattern>=<level> (e.g. eth/*=5,p2p=4)
  --backtrace value         Request a stack trace at a specific logging statement (e.g. "block.go:271")
  --debug                   Prepends log messages with call-site location (file and line number)
  --pprof                   Enable the pprof HTTP server
  --pprofaddr value         pprof HTTP server listening interface (default: "127.0.0.1")
  --pprofport value         pprof HTTP server listening port (default: 6060)
  --memprofilerate value    Turn on memory profiling with the given rate (default: 524288)
  --blockprofilerate value  Turn on block profiling with the given rate (default: 0)
  --cpuprofile value        Write CPU profile to the given file
  --trace value             Write execution trace to the given file
  --wasmlog value           output wasm contract log to file

METRICS AND STATS OPTIONS:
  --metrics                          Enable metrics collection and reporting
  --metrics.expensive                Enable expensive metrics collection and reporting
  --metrics.influxdb                 Enable metrics export/push to an external InfluxDB database
  --metrics.influxdb.endpoint value  InfluxDB API endpoint to report metrics to (default: "http://localhost:8086")
  --metrics.influxdb.database value  InfluxDB database name to push reported metrics to (default: "alaya")
  --metrics.influxdb.username value  Username to authorize access to the database (default: "test")
  --metrics.influxdb.password value  Password to authorize access to the database (default: "test")
  --metrics.influxdb.tags value      Comma-separated InfluxDB tags (key/values) attached to all measurements (default: "host=localhost")

CBFT OPTIONS:
  --cbft.msg_queue_size value      Message queue size (default: 1024)
  --cbft.wal.disabled              Disable the Wal server
  --cbft.max_ping_latency value    Maximum latency of ping (default: 2000)
  --cbft.blskey value              BLS key file
  --cbft.blacklist_deadline value  Blacklist effective time. uint:minute (default: "60")

DB OPTIONS:
  --db.nogc               Disables database garbage collection
  --db.gc_interval value  Block interval for garbage collection (default: 86400)
  --db.gc_timeout value   Maximum time for database garbage collection (default: 1m0s)
  --db.gc_mpt             Enables database garbage collection MPT
  --db.gc_block value     Number of cache block states, default 10 (default: 10)

VM OPTIONS:
  --vm.wasm_type value         The actual implementation type of the wasm instance (default: "wagon")
  --vm.timeout_duration value  The VM execution timeout duration (uint: ms) (default: 0)

MISC OPTIONS:
  --help, -h  show help


COPYRIGHT:
   Copyright 2019 The Alaya-Go Authors
```
---

## 常用rpc命令

- 说明
  - rpc端口根据实际的启动命令进行变更，默认为：6789

### admin

- 查看当前节点数据目录

  ```bash
  alaya attach http://localhost:6789 -exec admin.datadir
  ```

- 查看当前节点的ChainID

  ```bash
  alaya attach http://localhost:6789 -exec admin.nodeInfo.protocols.platon.config.chainId
  ```

- 查看当前节点的id

  ```bash
  alaya attach http://localhost:6789 -exec admin.nodeInfo.id
  ```

- 查看当前节点的blsPubKey

  ```bash
  alaya attach http://localhost:6789 -exec admin.nodeInfo.blsPubKey
  ```

- 查看当前节点的p2p端口号

  ```
  alaya attach http://localhost:6789 -exec admin.nodeInfo.ports.listener
  ```

- 查看当前节点的peers的连接信息

  ```bash
  alaya attach http://localhost:6789 -exec admin.peers
  ```

- 查看当前节点的创世区块hash

  ```bash
  alaya attach http://localhost:6789 -exec admin.nodeInfo.protocols.platon.genesis
  ```

- 查看cbft共识每个共识轮单个节点的最大出块数($amount)

  ```bash
  alaya attach http://localhost:6789 -exec admin.nodeInfo.protocols.platon.config.cbft.amount
  ```

- 查看cbft共识每个共识轮单个节点的出块的时间窗口（$period，单位：ms）

  ```bash
  alaya attach http://localhost:6789 -exec admin.nodeInfo.protocols.platon.config.cbft.period
  ```

  >**出块时间间隔 = period / 1000 / amount**

- 获取二进制版本号和签名信息

  ```bash
  alaya attach http://localhost:6789 -exec 'admin.getProgramVersion()'
  ```

- 获取零知识证明信息（用节点私钥去证明该接口出的证明是否正确，用于节点质押）

  ```bash
  alaya attach http://localhost:6789 -exec 'admin.getSchnorrNIZKProve()'
  ```

- 查看底层使用的虚机类型（EVM/WASM）

  ```bash
  alaya attach http://localhost:6789 -exec admin.nodeInfo.protocols.platon.config.interpreter
  ```

### platon

- 查看当前节点下所有的钱包地址

  ```bash
  alaya attach http://localhost:6789 -exec platon.accounts
  ```

- 查看当前节点的块高

  ```bash
  alaya attach http://localhost:6789 -exec platon.blockNumber
  ```

- 查询指定账户的余额($account为账户地址)

  ```bash
  alaya attach http://localhost:6789 -exec 'platon.getBalance("$account")'
  ```

- 查询指定块的交易数量($blockNumber为指定块的块高或区块hash)

  ```bash
  alaya attach http://localhost:6789 -exec 'platon.getBlockTransactionCount($blockNumber)'
  ```

- 查询交易信息($txHash为交易hash)

  ```bash
  alaya attach http://localhost:6789 -exec 'platon.getTransaction("$txHash")'
  ```

- 查询交易回执($txHash为交易hash)

  ```bash
  alaya attach http://localhost:6789 -exec 'platon.getTransactionReceipt("$txHash")'
  ```

- 查询指定账户的交易数（参数$address为账户地址，用于发交易时指定交易的nonce）

  ```bash
  alaya attach http://localhost:6789 -exec 'platon.getTransactionCount("$address")'
  ```

- 查询当前节点正在pending的交易

  ```bash
  alaya attach http://localhost:6789 -exec platon.pendingTransactions
  ```

- 查看当前节点默认的gasPrice(单位：von)

  ```bash
  alaya attach http://localhost:6789 -exec platon.gasPrice
  ```

- 预估交易的gas(参数$transaction为交易详情，单位：von)

  ```bash
  alaya attach http://localhost:6789 -exec 'platon.estimateGas($transaction)'
  ```

  如：

  ```bash
  alaya attach http://localhost:6789 -exec 'platon.estimateGas({from:"lax1fyeszufxwxk62p46djncj86rd553skpptsj8v6",to:"lax1zhllhqu72wz66cdwly8983xhla2sann75j2ec2",value:"0x10000000000000",data:"0x11",gas:"0x88888",gasprice:"0x333333",nonce:"11"})'
  ```

- 查看当前节点底层版本的p2p协议号

  ```bash
  alaya attach http://localhost:6789 -exec 'web3.toDecimal(platon.protocolVersion)'
  ```

- 查看当前节点是否在同步

  ```bash
  alaya attach http://localhost:6789 -exec platon.syncing
  ```

- 获取指定区块详情

  ```bash
  alaya attach http://localhost:6789 -exec 'platon.getBlock($blockNumber)
  ```

### personal

- 生成钱包(参数为钱包密码)

  ```bash
  alaya attach http://localhost:6789 -exec 'personal.newAccount("88888888")'
  ```

- 导入私钥，生成钱包

  ```bash
  alaya attach http://localhost:6789 -exec 'personal.importRawKey($privateKey,$password)'
  ```

  > 参数：
  >
  > - privateKey：私钥，去除开头的0x
  > - password：钱包密码
  >
  > 返回：
  >
  > - 钱包地址

  例子：

  ```bash
  alaya attach http://localhost:6789 -exec 'personal.importRawKey("842d943dbb50a8d3fe63af2f82fda3d8f0ca817fe8d47e61698142bac7c24212","88888888")'
  ```

- 查看账户地址

  ```bash
  alaya attach http://localhost:6789 -exec 'personal.listAccounts'
  ```

- 查看本地钱包信息，包括钱包地址，钱包文件路径，钱包状态

  ```bash
  alaya attach http://localhost:6789 -exec 'personal.listWallets'
  ```

- 锁账户

  ```bash
  alaya attach http://localhost:6789 -exec 'personal.lockAccount(platon.accounts[0])'
  ```

- 解锁账户

  ```bash
  alaya attach http://localhost:6789 -exec 'personal.unlockAccount(platon.accounts[0],"88888888",24*3600)'
  ```

  > 参数：
  >
  > - 账户地址
  > - 钱包密码
  > - 解锁时间，单位：秒

  - 发送未签名的交易

  ```shell
  alaya attach http://localhost:6789 -exec 'personal.sendTransaction({from:platon.accounts[2],to:platon.accounts[0],value:web3.toVon("0.1","lat"),nonce:platon.getTransactionCount(platon.accounts[2])},"88888888")'
  ```

### net

- 查看当前节点的networkid

  ```bash
  alaya attach http://localhost:6789 -exec net.version
  ```

- 查看当前节点的p2p端口是否处于监听状态

  ```bash
  alaya attach http://localhost:6789 -exec net.listening
  ```

- 查看当前节点的peers连接数

  ```bash
  alaya attach http://localhost:6789 -exec net.peerCount
  ```

### debug

- 查询当前节点经济模型配置参数

  ```bash
  alaya attach http://localhost:6789 -exec 'debug.economicConfig()'
  ```

- 设置日志级别

  ```shell
  alaya attach http://localhost:6789 -exec 'debug.verbosity(4)'
  ```

  >日志级别说明：
  >
  >0：CRIT
  >
  >1：ERROR
  >
  >2：WARN
  >
  >3：INFO
  >
  >4：DEBUG
  >
  >5：TRACE

## alayakey工具使用说明

```conf

alayakey [global options] command [command options] [arguments...]

VERSION:
   0.14.0-unstable-16aced7d

COMMANDS:
   generate          generate new keyfile
   inspect           inspect a keyfile
   changepassphrase  change the passphrase on a keyfile
   signmessage       sign a message
   verifymessage     verify the signature of a signed message
   genkeypair        generate new private key pair
   genblskeypair     generate new bls private key pair
   updateaddress     update hex/bech32 address to mainnet/testnet bech32 address
   help              Shows a list of commands or help for one command
   
GLOBAL OPTIONS:
   --help, -h     show help
   --version, -v  print the version

```

### 常用命令

1. 生成钱包

```conf
NAME:
   alayakey generate - generate new keyfile

USAGE:
   alayakey generate [command options] [ <keyfile> ]

DESCRIPTION:
   
Generate a new keyfile.

If you want to encrypt an existing private key, it can be specified by setting
--privatekey with the location of the file containing the private key.


OPTIONS:
   --passwordfile value  the file that contains the passphrase for the keyfile
   --json                output JSON instead of human-readable format
   --privatekey value    file containing a raw private key to encrypt
```

可以通过以下命令生成一个新的钱包

```shell
alayakey generate
```

也可以使用以下命令将一个privatekey明文加密生成一个钱包文件

```shell
alayakey generate --privatekey ./prikey --json
```

2. 生成公私钥对

生成节点公私钥：
```conf
NAME:
   alayakey genkeypair - generate new private key pair

USAGE:
   alayakey genkeypair [command options] [ ]

DESCRIPTION:
   
Generate a new private key pair.


OPTIONS:
   --json  output JSON instead of human-readable format
```


生成节点BLS公私钥

```conf
NAME:
   alayakey genblskeypair - generate new bls private key pair

USAGE:
   alayakey genblskeypair [command options] [  ]

DESCRIPTION:
   
Generate a new bls private key pair.


OPTIONS:
   --json  output JSON instead of human-readable format
```

3. 将任意EIP55/bech32地址转换为alaya地址

```conf
NAME:
   alayakey updateaddress - update hex/bech32 address to mainnet/testnet bech32 address

USAGE:
   alayakey updateaddress [command options] [<address> <address>...]

DESCRIPTION:
   
update hex/bech32 address to mainnet/testnet bech32 address.


OPTIONS:
   --json                  output JSON instead of human-readable format
   --hexAddressFile value  file bech32/hex accounts want to update to mainnet/testnet bech32 address,file like  [hex,hex...]
```

以下命令将EIP55地址转换为alaya地址

```shell
alayakey updateaddress 0x1000000000000000000000000000000000000001
```

此命令支持将任意bech32地址转换为alaya地址，如：

```shell
alayakey updateaddress lax19phpafljm0mgu2fj8mrwyarftpafynxvj0d7lh
originAddress:  lax19phpafljm0mgu2fj8mrwyarftpafynxvj0d7lh
main net Address: atp19phpafljm0mgu2fj8mrwyarftpafynxvyuffwh
other net Address: atx19phpafljm0mgu2fj8mrwyarftpafynxvw64raa
```
