## parity-bitcoin/chain/transaction.rs


交易结构在wiki上写的很清楚了，我就不在这重复写了

## 常量
WITNESS_MARKER
WITNESS_FLAG

这俩我回头再来看吧....

## struct

### Outpoint
代表一个交易在区块链具体位置的索引，hash是区块hash，index是对应编号

#### is_null()
判断索引是否为空

### TransactionInput
交易输入，包含的东西有之前的未花费交易输出，签名，序列号（用来在锁定时间之前更改交易），script_witness（又是这东西）


#### coinbase()
无中生钱的函数

#### is_final()
是否是最终的那个交易

#### has_witness()
是否有witness

#### HeapSizeOf
堆大小

### TransactionOutput
包括值和公钥

#### Default
估计就是给TransactionOutput整个默认值吧

#### HeapSizeOf
堆大小

### Transaction
version：协议的版本，输入，输出，锁定时间

#### From
把16进制的数据弄成数据结构的亚子

### HeapSizeOf
还是堆大小

### 一堆方法
hash：计算交易的hash
witness_hash：witness的hash
inputs：交易输入
outputs：交易输出
is_empty：交易是否没有输出
is_null：交易是否没有输入
is_coinbase：是不是一个造币交易
is_final：是不是最终的交易，如果锁定时间为0或者交易输入是判断是最终的了，那么这就是最终的交易了
is_final_in_block：如果锁定时间等于0或者锁定时间小于当前的区块高度，那么这个交易就是区块中的最后交易了，否则就要看看所有交易输入是否都是所有交易输入了，如果输入里面所有交易输入都是最终输入，那么就是最终交易了
has_witness：是否有见证数据
total_spends：总共的花费，所有输出的值加起来

## 方法
transaction_hash：计算交易hash

## 测试
test_transaction_reader：测试交易读取
test_transaction_hash：测试交易hash
test_transaction_serialized_len：测试交易序列化函数对不对
test_transaction_reader_with_witness：测试含见证的数据对不对
test_serialization_with_flags：测试有见证的序列化函数对不对
test_witness_hash_differs：测试有无见证的交易的hash是否会产生不同