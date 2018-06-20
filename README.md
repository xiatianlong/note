# **钱包接口需求文档**

###  Web后台
###### 提供用户的管理。提供创建链与交易查询功能。有新用户是创建链，将链标识提供给用户，用户对钱包的接口请求都需要带上链标识。

> **创建区块链**

createChain();

	创建区块链，返回链标识
	
> **交易查询**

selectTransaction(String transactionId) // 交易ID标识，请求钱包接口
	查询交易信息



###  钱包
###### 用户使用。 用户请求生成地址，接口返回加密后的助记词，并持久化地址。当用户请求交易时，对传递的助记词进行解密并生成地址（校验地址在持久化的数据库中是否存在），然后进行交易处理。
> **生成地址**

createWallet(String chainId); // 链标识

	根据"链ID"生成助记词->秘钥->地址，(持久化存储)，返回助记词（加密）
	
> **交易**

transaction(String mnemonic, String toAddr, long coin); // 助记词（加密），接收方地址，交易金额

	根据"链ID",打包交易信息，推送到指定的区块链。（持久化存储）,返回交易ID标识

> **交易查询**

selectTransaction(String transactionId) // 交易ID标识

	查询交易信息
	
> **余额查询**

getBalance(String addr) // 地址

	查询余额





