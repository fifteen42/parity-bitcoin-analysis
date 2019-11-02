## parity-bitcoin/chain/constant.rs

这几个参数是 BIP 68 的应用

BIP 68 主要是对比特币交易序列号的一些更改设置。

比特币交易的每一个输入都有对应的序列号。最开始的想法是矿工应该优先选择序列号高的交易，但由于矿工只会只会选取利益最大化的交易，所以最开始关于序列号的想法从来没实现过。所以 BIP 68 就想把交易输入序列号用作其他用途，并且也预留了一些空间为以后的更改做准备。

交易的 nLockTime 可以用于设置交易的被挖矿的时间。nSequence 则被重新构想用于在指定输出时间被挖矿。这是双向支付通道的基础之一。

### SEQUENCE_LOCKTIME_DISABLE_FLAG
如果这个参数被设置了，那么就代表 sequence number 没啥实际意义。反之，序列号就会被解释为对应的 nLockTime。

### SEQUENCE_FINAL
这个估计就是就是序列号。disables nLockTime 是指不包括锁定时间吗？

### SEQUENCE_LOCKTIME_TYPE_FLAG
这个值如果被设置了，锁定时间就会以时间为单位。没有被设置的话，就会以区块数为单位

### SEQUENCE_LOCKTIME_MASK
作为relative lock-time的摘要

### LOCKTIME_THRESHOLD
lock-time 的阈值，LOCKTIME 如果低于此值将会被认为是区块号。

### SATOSHIS_IN_COIN
一个比特币可以分为几个 Satoshis