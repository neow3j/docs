# 部署智能合约

智能合约的部署是将智能合约部署到区块链中，供其它用户使用或者供其它智能合约调用。本文将介绍如何使用 Neo-GUI 在 Neo 区块链上部署智能合约。本文中的操作步骤是通用的，适用于包括 NEP5 代币在内的所有合约类型。

## 什么需要部署？

当一个智能合约要被其它智能合约调用（称为 appcall）时，需要部署。而仅由合约账户鉴权触发的合约，如锁仓合约、多方签名合约，不会被其它合约调用，所以无需部署。 “Return 1+1” 这样的合约，因为没有任何需要输入的参数，也无需部署。 

从编程语言的角度来说，当智能合约要作为一个类库使用时，才需要被部署。比如以下情况：

- 当一个智能合约有可变的传入参数，此时它必须作为一个类库，由调用者（Invocation 交易）或者其它的智能合约提供参数。
- 当一个智能合约使用存储区（Storage）与动态调用（NEP4）时，必须作为一个类库。
- 当一个智能合约实现了 NEP-5（合约资产）时，需要将该合约部署到区块链上。

智能合约的部署是通过 Invocation 交易调用 API 来部署（旧版的系统中是以 Publish 交易来部署的，目前已经弃用）。通常的做法是通过 Neo-GUI 的智能合约发布功能来部署合约。

部署智能合约以及调用智能合约均会产生费用，详情请参见 [系统手续费](../fees.md)。

## 准备工作
在开始部署之前，请确认您已经完成以下工作：

- 已确认您的合约需要部署。
- 已编译好一个 .avm 合约文件。
- 已安装 Neo-GUI 并完成区块同步。相关信息请参阅 [使用 Neo-GUI 客户端](../../node/gui/install.md)。

## 使用 Neo-GUI 部署智能合约

1. 在 Neo-GUI 中点击 `高级` -> `部署合约`。

2. 在部署合约对话框中，点击 `加载` 选择编译好的合约文件。

   此时代码框中会显示合约脚本。将其复制供以后使用。

3. 填写信息与元数据区域的参数。

   元数据参数填写可参考 [智能合约参数和返回值](Parameter.md)。

   如果需要，勾选 `需要创建存储区`。NEP5 标准使用存储区来维护帐户，因此部署 NEP5 token 时请勾选此项。

4. 完成所有参数填写后，点击 `部署`。

   部署合约需要花费100 ~1000 GAS，详情请参见 [系统手续费](../fees.md)。

## 创建智能合约地址   

如果合约需要接受资产交易，你需要使用合约脚本创建一个合约地址。

1. 创建好钱包后，在 Neo-GUI 中点击鼠标右键，选择 `创建合约地址` -> `自定义`。
2. 在 `导入自定义合约` 对话框中设置以下选项：
  
   a. `形参列表`：参考 [智能合约参数和返回值](Parameter.md)
   
   b. `脚本代码`：填写上一步复制的合约脚本代码。
   
   c. `私钥`：可选参数，当合约执行过程中需要签名时，设置用于签名的私钥。
   
3. 点击 `确定`。

