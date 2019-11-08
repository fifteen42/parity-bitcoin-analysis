# Parity Bitcoin 源码分析
主要是写来帮助自己理解区块链以及Rust的，预计会有很多坑。终极目标是能根据文档重写客户端_(:зゝ∠)_ 

## 形式
看完代码之后想有一点输出，就在对应的md文件里面写了。可能包括原理解释、编码技巧、引用的库的介绍、遗留问题等

每个文件夹都会有一个综述性的介绍，然后每个具体的文件都会有对应的介绍

## 进度

### chain

- [x] block_header
- [x] block
- [x] constant
- [x] indexed_block
- [x] indexed_header
- [x] indexed_transaction
- [ ] lib
- [x] mekle_root
- [ ] read_and_hash
- [x] transaction

## 参考材料
主要参考的东西基本都是官方材料，以及一些权威一点的书籍:

- [比特币白皮书](https://bitcoin.org/bitcoin.pdf)
- 精通比特币: [英文版](https://github.com/bitcoinbook/bitcoinbook)  [中文版](https://github.com/tianmingyun/MasterBitcoin2CN)
- [Bitcoin Wiki](https://github.com/bitcoinbook/bitcoinbook)
- [比特币改进协议](https://github.com/bitcoin/bips)
- [The Rust Programming Language](https://doc.rust-lang.org/book/) （ [中文版](https://rustlang-cn.org/office/rust/book/) ）
- [Rust 文档](https://doc.rust-lang.org/std/index.html)

