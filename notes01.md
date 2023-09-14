### home-credit-default-risk

许多人由于信用记录不足或不存在而难以获得贷款。不幸的是，这个群体经常被不值得信赖的贷款人利用。

捷信致力于通过提供积极、安全的借贷体验来扩大无银行账户人群的金融包容性。为了确保这些服务不足的人群获得积极的贷款体验，捷信利用各种替代数据（包括电信和交易信息）来预测客户的还款能力。

虽然捷信目前正在使用各种统计和机器学习方法来做出这些预测，但他们正在向 Kaggler 提出挑战，要求他们帮助他们释放数据的全部潜力。这样做将确保有能力还款的客户不会被拒绝，并且贷款的本金、到期日和还款日历将有助于客户取得成功。

评价：
提交的内容根据预测概率与观察目标之间的 ROC 曲线下面积进行评估。(AUC)

对于测试集中的每个 SK_ID_CURR，您必须预测 TARGET 变量的概率。该文件应包含标头并具有以下格式：

#### Data Exploration

##### application_{train|test}.csv

这是主表，分为两个文件：训练（带目标）和测试（不带目标）。
所有应用程序的静态数据。 一行代表我们数据样本中的一笔贷款。
##### bureau.csv

向信用局报告的其他金融机构提供的所有客户之前的信用（对于我们样本中拥有贷款的客户）。
对于我们样本中的每笔贷款，行数与客户在申请日期之前在信用局拥有的信用数一样多。



##### Bureau_balance.csv

信用局以前信用的每月余额。
该表有一行记录向征信局报告的每个先前信用的历史记录 - 即该表具有（样本中的贷款数 * 相对先前信用数 * 我们可以观察到先前信用的历史记录的月份数）行 。

##### POS_CASH_balance.csv

申请人之前通过捷信获得的 POS（销售点）和现金贷款的每月余额快照。
该表有一行记录了与我们样本中的贷款相关的捷信（消费信贷和现金贷款）中每笔先前信用的历史记录，即该表具有（样本中的贷款数 * 相关先前信用数 * 月数） 其中我们可以观察到之前的制作人员行的一些历史记录。

##### credit_card_balance.csv

申请人之前在捷信持有的信用卡的每月余额快照。
该表有一行记录了与我们样本中的贷款相关的捷信（消费信贷和现金贷款）中每笔先前信用的历史记录，即该表具有（样本中的贷款数 * 相关先前信用卡的数量 * 的数量） 我们对之前的信用卡行有一些可观察到的历史记录。
##### previous_application.csv

我们样本中拥有贷款的客户之前所有捷信贷款申请。
在我们的数据样本中，与贷款相关的每个先前申请都有一行。
##### installments_payments.csv

与我们样本中的贷款相关的捷信之前发放的信贷的还款历史记录。
a`)` 每笔付款占一行，b`)` 错过的付款各占一行。
一行相当于一笔分期付款，或者一笔分期付款对应于与我们样本中的贷款相关的一份先前捷信信贷的一笔付款。


##### HomeCredit_columns_description.csv

该文件包含各个数据文件中的列的描述。

需要用ISO-8859-1解码


#### Features Engineering

清洗后的features数据可以在此路径下载：[features.csv](https://hkustconnect-my.sharepoint.com/:x:/g/personal/jwangiy_connect_ust_hk/Eb2o_OS3WUBFoebOz7o0ZKUBbGwSKCqmxeu7jgPjybU0lQ?e=tETc40) 

#### 模型开发、验证和结果
mafs6010z-warmup2.ipynb

模型[lgb.pkl](https://hkustconnect-my.sharepoint.com/:u:/g/personal/jwangiy_connect_ust_hk/EXObQJkzq5ZNhMZan55IvRcBZaCPWSMeZoff2KSPOv-zSg?e=48lNnx) 

入模特征[feacols2.pkl](https://hkustconnect-my.sharepoint.com/:u:/g/personal/jwangiy_connect_ust_hk/Ee1RgoaxkWdJkdShoiZpEJkB1YVbjfcHIwWEJnDw5V8OUQ?e=d7cxPP)

结果[submission.csv](https://hkustconnect-my.sharepoint.com/:x:/g/personal/jwangiy_connect_ust_hk/EVy07ql7IitJmlzS__SApYABEv_rhzk9zSTv12x3wVkB-A?e=77MPMI)
