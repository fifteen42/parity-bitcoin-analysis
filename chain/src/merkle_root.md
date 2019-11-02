## parity-bitcoin/chain/merkle_root.md

## 函数

### concat()
把两个 hash256 的值合并成一个 hash512的值

### merkle_root()
计算区块的merkle_root。merkle tree是一个满二叉树，这个二叉树的叶子节点，是交易的两次哈希，如果交易是奇数，那么最后一个交易的两次hash就再重复一次。

上一高度的节点是由其两个子节点计算两次hash得来，直至产生二叉树的根节点，这个根节点的值就是merkle_root.

### par_iter()
并行计算

### merkle_node_hash()
计算两个节点的两次 hash

## test

### test_merkle_root_with_2_hashes()
计算两个 hash 的 merkle 根

### test_merkle_root_with_5_hashes()
计算五个 hash 的 merkle 根

