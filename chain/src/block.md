## parity-bitcoin/chain/block.rs

## struct

区块是区块链的基础结构，主要由区块头和交易数据构成。具体结构如下：

|Field	    |Description	                                   |Size|
|  ----  | ----  | ----  |
|Magic no	|value always 0xD9B4BEF9	                       |4 bytes|
|Blocksize	|number of bytes following up to end of block   |4 bytes|
|Blockheader	  | consists of 6 items	|80 bytes|
|Transaction     |counter	positive integer VI = VarInt	|       1 - 9 bytes|
|transactions	|the (non empty) list of transactions	  | <Transaction counter>-many transactions|

在源码中看到只出现了两个字段，不知道其他的三个字段会在哪里体现。

``` Rust
pub struct Block {
	pub block_header: BlockHeader,
	pub transactions: Vec<Transaction>,
}
```

## trait

### From<&'static str>
把字符串转化为区块，估计就是把十六进制的那种数据转化成能看的那种数据结构

## method

### new()

输入区块头和交易数据然后创建新的区块

### merkle_root()

根据交易数据计算对应的 merkle 根

### witness_merkle_root()

计算另外一种 merkle 根，用于隔离见证

### transactions()

返回交易

### header()

返回区块头

### hash()

返回区块头的 hash


## 测试

测试了一下merkle根和hash正不正确
