## parity-bitcoin/network/network.rs

首先解释一下幻数（magic number），虽然听起来好像很牛逼，但是这个东西就是中本聪用来标记哪里是区块的开头而设置的常量😅

### 枚举类型 Network

- Mainnet：比特币主网，比特币在这里具有真实的经济价值
- Testnet：比特币主网的测试网
- Regtest：和测试网比较像的一个私有的测试节点
- Unitest：用于单元测试的测试网，工作量证明的难度为0
- Other：其他的网络，默认和比特币主网一致

### impl

magic：区分各种状态的网，以及BCC还是BTC 
max_bits：根据网络来匹配这个值，俺也不知道这个值是干啥的
port：根据网络来匹配端口号
rpc_port：匹配另一种端口号？
genesis_block：根据网络来分发创世区块
default_verification_edge：这又是返回的啥？s

### 测试

就是测试几个值是否和规定的值相同。


总体来说这个文件就是根据网络来返回各种参数，今天好困不想细看每个参数了，改天再来看吧...



