# 注册与分发资产

## 注册资产

您可以在 Neo 区块链中创设一种新的发行资产，可以自己定义资产的类型、名称、总量等，并指定资产的管理员账户。创设资产需要消耗一定数量的 GAS 作为附加服务费，目前为 4990 GAS。

资产类型有两种，代币（Token） 和 股份 （Share，转账时需要双方签名）。以下操作步骤以 Token 为例：     

1. 在 Neo-GUI 中点击 `高级` -> `注册资产`。填写以下选项并点击 `确定`：

   - 资产种类：设置资产类型：代币（Token）或 股份 （Share）
   - 名称：设置资产名称。资产发行后，可以在neo-gui的资产页签中或者区块链浏览器中查看到资产名称。
   - 总量限制：如果要限制资产发行总量，选取此项并设置上限。
   - 精度：资产的最小单位数。默认为8，表示最小单位为0.00000001。如果设置为0，表示最小单位为1。
   - 发行者：设置资产的发行者。
   - 管理员：管理员可以修改资产的名称、总量等。目前功能尚未支持。
   - 分发：设置分发资产的地址。

   ![](../assets/gui_43.png)

2. 注册资产通过调用智能合约来完成，在出现的调用合约窗口中点击`试运行`，即可看到所需手续费详情：

   同时，您也可以选择加载本地写好的智能合约文档。     

   需要注意的是，注册资产需花费大量手续费（目前为 4990 GAS），请谨慎操作。 

3. 确认注册资产，点击 `调用`。

4. 返回交易成功结果，复制交易ID并粘贴到记事本，以备资产分发时使用。

   您也可以在交易记录中查看到注册资产的交易编号并右键单击复制交易ID。     

> [!Note]
>
> 注册资产后需要等待约15分钟才能分发资产。

## 分发资产

完成资产注册后，就可以在资产创设所设定的总量上限范围内，向发行人指定的地址中发放该资产。分发后的资产可以用于转账和交易。分发资产需要消耗一定数量的 GAS 作为附加服务费，目前为1 GAS。

1. 在 Neo-GUI 中点击 `高级` -> `分发资产`。

2. 将在注册资产最后一步中复制的交易ID粘贴到`资产 ID`中，会自动显示对应的资产详情。

   如果交易ID以 ”0x“ 开始，需要删去”0x“ 再输入。

3. 点击加号按钮输入要分发资产的账户地址和数额，点击确定。

   分发完毕后可以在钱包资产中查看到用户创设的资产。

![](../assets/gui_46.png)      

> [!Note]
>
> 每次分发资产需花费手续费（目前为 1 GAS），请谨慎操作，可以选择一次性批量分发以节省费用。