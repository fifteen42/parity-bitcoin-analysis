## parity-bitcoin/chain/indexed_block.rs
## parity-bitcoin/chain/indexed_header.rs
## parity-bitcoin/chain/indexed_transaction.rs

是block、block_header、transaction的index版本，主要添加了这几个功能：

1. 普通structure与index版的互相转化
2. 与其他indexed的hash比较
3. deserialize方法

