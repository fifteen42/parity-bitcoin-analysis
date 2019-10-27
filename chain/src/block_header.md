## parity-bitcoin/chain/block_header.rs

区块头包含以下字段

|Field	|Purpose	|Updated when...	|Size (Bytes)|
|---|---|---|---|
|Version	|Block version number	|You upgrade the software and it specifies a new version|	4|
|hashPrevBlock	|256-bit hash of the previous block header	|A new block comes in|	32|
|hashMerkleRoot	|256-bit hash based on all of the transactions in the block	|A transaction is accepted|	32|
|Time	|Current block timestamp as seconds since 1970-01-01T00:00 UTC	|Every few seconds|	4|
|Bits	|Current target in compact format	|The difficulty is adjusted|	4|
|Nonce	|32-bit number (starts at 0)	|A hash is tried (increments)|	4|

## 方法

### hash()

计算区块头的hash

## trait

### fmt::Debug

作用是打印区块头

### From<&'static str>
把字符串转化为区块头，估计就是把十六进制的那种数据转化成能看的那种数据结构

## 函数

### block_header_hash
真正计算 hash 的函数是这个

## 测试

### test_block_header_stream()

测试区块头能不能正确转成对应数据（说实话有点不明白这个stream）

### test_block_header_reader()

测试一下 Reader 能不能行，和上面这个函数是逆过程吧




