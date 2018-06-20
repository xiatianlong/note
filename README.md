# **钱包需求文档**

###  Web后台
###### 提供用户的管理

> **创建区块链**
createChain();

	创建区块链，返回链标识
> **交易查询**
selectTransaction(String transactionId) // 交易ID标识
	查询交易信息



###  钱包
###### 用户使用
> **生成地址**
createWallet(String chainId); // 链标识

	根据"链ID"生成助记词->秘钥->地址，(持久化存储)，返回助记词（加密）
	
> **交易**
transaction(String mnemonic, String toAddr, long coin); // 助记词（加密），接收方地址，交易金额

	根据"链ID",打包交易信息，推送到指定的区块链。（持久化存储）,返回交易ID标识







