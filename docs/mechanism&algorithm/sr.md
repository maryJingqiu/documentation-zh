## 超级代表与委员会

<h3>1. 申请成为超级代表候选人规则 </h3>

 在TRON网络中，任何账户都可以申请成为超级代表候选人，都有机会成为超级代表。每个账户都可以投票给超级代表候选人，获取投票数最高的27个超级代表候选人就是超级代表。就具有出链块的权利。
 投票统计每6小时统计一次，超级代表也就每6个小时变更一次。

 为了防止恶意攻击，成为超级代表候选人也需要一定代价的。TRON网络将直接烧掉申请者账户9999TRX。申请成功后，您就可以竞选超级代表了。

<h3>2. 选举超级代表 </h3>

 投票需要TRON Power(TP)，你的TRON Power(TP)的多少由当前冻结资金决定。TRON Power(TP)的计算方法：每冻结1TRX，就可以获得1单位TRON Power(TP)。

 TRON网络中的每一个账户都具有选举权，可以通过投票选出自己认同的超级代表了。

 在解冻后，你没有了冻结的资产，相应地失去了所有的TRON Power(TP)，因此以前的投票会失效。你可以通过重新冻结并投票来避免投票失效。

注意: 波场网络只记录你最后一次投票的状态，也就是说你的每一次投票都会覆盖以前所有的投票效果

+ 示例：

```
freezebalance 10,000,000 3 // 冻结了10TRX，获取了10单位TRON Power(TP)
votewitness witness1 4 witness2 6 // 同时给witness1投了4票，给witness2投了6票
votewitness witness1 3 witness2 7 // 同时给witness1投了3票，给witness2投了7票
```

以上命令的最终结果是给witness1投了3票，给witness2投了7票

<h3>3. 超级代表的奖励 </h3>

1.&nbsp;票数奖励  
每6小时，票数排名前127名的超级代表会获得共计115,200 TRX的票数奖励，这部分奖励将按照票数比例分发。每年的票数奖励总计168,192,000 TRX。

2.&nbsp;出块奖励  
波场协议网络每3秒中会出一个区块，每个区块将给予超级代表32个TRX奖励，每年总计336,384,000 TRX将会被奖励给超级代表。    
超级代表每次出块完成后，出块奖励都会发到超级代表的子账号当中，超级代表不能直接使用这部分资产，但可以查询。 每24h允许一次提取操作。从该子账号转移到超级代表的账户中。  

<h3> 4. 委员会 </h3>

<h4> 4.1 什么是委员会 </h4>
委员会用于修改Tron网络动态参数，如出块奖励、交易费用等等。委员会由当前的27个超级代表组成。每个超级代表都具有提议权、对提议的投票权，
当提议获得19个代表及以上的赞成票时，该提议获得通过，并在下个维护期内进行网络参数修改。

<h4> 4.2 创建提议 </h4>
只有超级代表对应账户具有提议权，其他账户无法创建提议。允许修改的网络动态参数以及编号如下( [min,max] )：

- 0: MAINTENANCE_TIME_INTERVAL, [3 * 27* 1000 ,24 * 3600 * 1000] // 修改超级代表调整时间间隔，目前为6 * 3600 * 1000ms  
- 1: ACCOUNT_UPGRADE_COST, [0,100 000 000 000 000 000]  // 修改账户升级为超级代表的费用，目前为9999000000 SUN  
- 2: CREATE_ACCOUNT_FEE, [0,100 000 000 000  000 000] // 修改创建账户费用，目前为100000 SUN  
- 3: TRANSACTION_FEE, [0,100 000 000 000 000 000] // 修改TRX抵扣带宽的费用，目前为10 SUN/byte  
- 4: ASSET_ISSUE_FEE, [0,100 000 000 000 000 000] // 修改资产发行费用，目前为1024000000 SUN  
- 5: WITNESS_PAY_PER_BLOCK, [0,100 000 000 000 000 000] // 修改超级代表出块奖励，目前为32000000 SUN  
- 6: WITNESS_STANDBY_ALLOWANCE, [0,100 000 000 000 000 000] // 修改分给前127名超级代表候选人的奖励，115200000000 SUN  
- 7: CREATE_NEW_ACCOUNT_FEE_IN_SYSTEM_CONTRACT, []// 修改系统创建账户的费用，目前为0 SUN  
- 8: CREATE_NEW_ACCOUNT_BANDWIDTH_RATE, // 提议7、8，组合使用，用于修改创建账户时对资源或TRX的消耗  
- 9: ALLOW_CREATION_OF_CONTRACTS, // 用于控制虚拟机功能的开启  
- 10: REMOVE_THE_POWER_OF_THE_GR  // 用于清除GR的创世票数  
- 11: ENERGY_FEE, [0,100 000 000 000 000 000] // SUN  
- 12: EXCHANGE_CREATE_FEE, [0,100 000 000 000 000 000] // SUN  
- 13: MAX_CPU_TIME_OF_ONE_TX, [0, 1000] // ms  
- 14: ALLOW_UPDATE_ACCOUNT_NAME, // 用于允许用户更改昵称以及昵称同名，目前为0，表示不允许  
- 15: ALLOW_SAME_TOKEN_NAME, // 用于允许创建相同名称的token，目前为0，表示不允许  
- 16: ALLOW_DELEGATE_RESOURCE, // 用于控制资源代理功能的开启  
- 17: TOTAL_ENERGY_LIMIT, // 用于调整Energy上限  
- 18: ALLOW_TVM_TRANSFER_TRC10, // 允许智能合约调用TRC10 token的接口，目前为0，表示不允许。设置为1表示允许
- 19: TOTAL_CURRENT_ENERGY_LIMIT, // 用于修改ENERGY总量, 目前为50000000000 SUN
- 20: ALLOW_MULTI_SIGN, // 用于多重签名，目前为1
- 21: ALLOW_ADAPTIVE_ENERGY, // 用于允许ENERGY总量自适应调整，目前为0，表示不允许
- 22: UPDATE_ACCOUNT_PERMISSION_FEE, // 用于修改账户权限费用，目前为100000000 SUN
- 23: MULTI_SIGN_FEE, // 用于修改多重签名费用，目前为1000000 SUN
- 24: ALLOW_PROTO_FILTER_NUM, // 用于允许更新protobuf的数字
- 25: ALLOW_ACCOUNT_STATE_ROOT, // 是否开启世界状态树
- 26: ALLOW_TVM_CONSTANTINOPLE, // 用于允许TVM支持君士坦丁堡更新
- 27: ALLOW_SHIELDED_TRANSACTION, // 允许匿名交易开启，目前为0，表示不允许
- 28: SHIELDED_TRANSACTION_FEE, [0,10 000 000 000] // 修改匿名交易手续费，目前为10
- 29: ADAPTIVE_RESOURCE_LIMIT_MULTIPLIER, [1,10 000] // 用于修改动态能量最大值，目前值为1000时，表示动态能量最大值是总能量的1000倍
- 30: ALLOW_CHANGE_DELEGATION, // 是否打开更换委托机制开关，目前为0，表示关闭
- 31: WITNESS_127_PAY_PER_BLOCK, [0,100 000 000 000 000 000] // 修改票数排名奖励，目前为16000000 SUN
- 32: ALLOW_TVM_SOLIDITY_059, // 允许虚拟机支持0.5.9版本的Solidity编译器，目前为0，表示不允许
- 33: ADAPTIVE_RESOURCE_LIMIT_TARGET_RATIO, [1,1 000] // 用于修改能量目标值，目前值为10时，表示为目标能量是总能量的1/10



+ 示例：
```text
createproposal id0 value0 ... idN valueN
id0_N: 参数编号
value0_N: 新参数值
```

注：Tron网络中，1 TRX = 1000_000 SUN。

<h4> 4.3 对提议进行投票 </h4>
提议仅支持投赞成票，不投票代表不赞同。从提议创建时间开始，3天时间内为提议的有效期。超过该时间范围，该提议如果没有获得足够的
赞成票，该提议失效。允许取消之前投的赞成票。


+ 示例：
```text
approveProposal id is_or_not_add_approval
id: 提议Id，根据提议创建时间递增
is_or_not_add_approval: 赞成或取消赞成
```

<h4> 4.4 取消提议 </h4>
提议创建者，能够在提议生效前，取消提议。

+ 示例：
```text
deleteProposal proposalId
id: 提议Id，根据提议创建时间递增
```

<h4> 4.5 查询提议 </h4>

以下接口可以查询提议，包括：  
查询所有提议信息（ListProposals）  
分页查询提议信息（GetPaginatedProposalList）  
查询指定提议信息（GetProposalById）       
相关api详情，请查询[Tron-http](Tron-http.md)  
