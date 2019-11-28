# 参数说明

> 提示💡：
>
> 1. 实际参数值以`cetcli query <module> params`命令返回值为准
> 2. 参数值中的CET均被放大了100000000倍
> 3. 关于StdTx签名数量上限的详细介绍，可以看[这篇文章](https://forum.coinex.org/t/msg/189)
> 4. 关于Gas价格的介绍，可以看[这篇文章](https://forum.coinex.org/t/coinex-gas-cli/170)

| 模块         | 参数名                            |           当前值 | 说明                                                         |
| ------------ | --------------------------------- | ---------------: | ------------------------------------------------------------ |
| alias        | fee_for_alias_length_2            |    1000000000000 | 10000CET，设置长度为2字符的别名时所收取的功能费              |
|              | fee_for_alias_length_3            |     500000000000 | 5000CET，设置长度为3字符的别名时所收取的功能费               |
|              | fee_for_alias_length_4            |     200000000000 | 2000CET，设置长度为4字符的别名时所收取的功能费               |
|              | fee_for_alias_length_5            |     100000000000 | 1000CET，设置长度为5字符的别名时所收取的功能费               |
|              | fee_for_alias_length_6            |      10000000000 | 100CET，设置长度为6字符的别名时所收取的功能费                |
|              | fee_for_alias_length_7_or_higher  |       1000000000 | 10CET，设置长度为7+字符的别名时所收取的功能费                |
|              | max_alias_count                   |                5 | 一个账户所能拥有的别名数量的上限                             |
| asset        | issue_rare_token_fee              |   10000000000000 | 100000CET，发行长度为2的Token费用                            |
|              | issue_token_fee                   |    1000000000000 | 10000CET，发行长度大于2的Token费用                           |
| auth         | max_memo_characters               |              512 | Memo长度（字节数）上限                                       |
|              | tx_sig_limit                      |                7 | StdTx签名数量上限                                            |
|              | tx_size_cost_per_byte             |               20 | 交易每字节Gas消耗                                            |
|              | sig_verify_cost_ed25519           |            11800 | ED25519验签Gas消耗                                           |
|              | sig_verify_cost_secp256k1         |            20000 | Secp256k1验签Gas消耗                                         |
|              | min_gas_price_limit               |             20.0 | 0.0000002CET，Gas价格下限                                    |
| bancorlite   | create_bancor_fee                 |      10000000000 | 100CET，创建Bancor所收取的功能费                             |
|              | cancel_bancor_fee                 |      10000000000 | 100CET，取消Bancor所收取的功能费                             |
|              | trade_fee_rate                    |               10 | 0.1%，Bancor交易的费率                                       |
| bank         | activation_fee                    |        100000000 | 1CET，激活账户费用                                           |
|              | lock_coins_free_time              |  604800000000000 | 7天，锁定转账的免费时长（单位是纳秒）                        |
|              | lock_coins_fee_per_day            |          1000000 | 0.01CET，锁定时长超过免费期后，每多一天所需要支付的费用（按天数取整） |
| distribution | community_tax                     |             0.02 | 2%，社区税比例                                               |
|              | base_proposer_reward              |             0.01 | 1%，基本的proposer奖励                                       |
|              | bonus_proposer_reward             |             0.04 | 4%，附加的proposer奖励                                       |
|              | withdraw_addr_enabled             |             true | 提款地址是否允许重置                                         |
| gov          | voting_params/voting_period       | 1209600000000000 | 14天，投票期限（单位是纳秒）                                 |
|              | tally_params/quorum               |              0.4 | 40%，有效提案需要达到的投票比例                              |
|              | tally_params/threshold            |              0.5 | 50%，**赞成**票占非弃权票票数的比例超过该值提案才能**通过**  |
|              | tally_params/veto                 |            0.334 | 33.4%，**强烈否决**票占总票数的比例超过该值则提案被**否决**  |
|              | deposit_params/min_deposit        | 1000000000000cet | 10000CET，提案最小充值（超过这个值提案才会进入投票阶段）     |
|              | deposit_params/max_deposit_period | 1209600000000000 | 14天，完成充值最长期限（单位是纳秒）                         |
| market       | create_market_fee                 |    1000000000000 | 10000CET，创建交易对市场的费用                               |
|              | fixed_trade_fee                   |          1000000 | 0.1CET，当订单创建时，订单中的stock与cet的交易对无历史成交价时，收取的固定费率 |
|              | market_min_expired_time           |  604800000000000 | 7天，发起交易对下线请求时，最快的下线时间间隔（单位是纳秒）  |
|              | gte_order_lifetime                |           100000 | 订单在dex上存在的区块梯度，单位是区块                        |
|              | gte_order_feature_fee_by_blocks   |               10 | 0.0000001CET。对于GTE类型的订单： 当订单在dex上存储的时间为[0,GTEOrderLifetime]区块时，不收取功能费； GTE Order在超过`GTEOrderLifetime`个区块之后, 超出的每个区块收取 `GTEOrderFeatureFeeByBlocks` |
|              | max_executed_price_change_ratio   |               25 | 25%，计算执行价格时的参考比例                                |
|              | market_fee_rate                   |               10 | 0.1%，订单的费率                                             |
|              | market_fee_min                    |          1000000 | 0.01CET，每笔最低需满足的手续费(来控制订单交易token的最小数量) |
|              | fee_for_zero_deal                 |          1000000 | 0.01CET，订单从链上删除时，无任何成交情况下，收取的手续费    |
| slashing     | max_evidence_age                  | 1814400000000000 | 14天，双签证据的最长有效期（单位是纳秒）                     |
|              | signed_blocks_window              |            10000 | Validator投票区块统计滑动窗口                                |
|              | min_signed_per_window             |             0.05 | 5%，滑动窗口内最少投票区块数，小于这个参数Validator就会因可用性差被惩罚 |
|              | downtime_jail_duration            |     600000000000 | 10分钟，可用性差关监狱时间（单位是纳秒）                     |
|              | slash_fraction_double_sign        |             0.05 | 5%，双签资金罚没比例                                         |
|              | slash_fraction_downtime           |           0.0001 | 0.01%，可用性差资金罚没比例                                  |
| staking      | unbonding_time                    | 1814400000000000 | 21天，Unbonding成熟时间（单位是纳秒）                        |
|              | max_validators                    |               42 | 验证者节点数量上限                                           |
|              | max_entries                       |                7 | undelegation/redelegation队列长度上限                        |
|              | bond_denom                        |              cet | 质押币种                                                     |
|              | min_self_delegation               |  500000000000000 | 5000000CET，节点最低自我质押金额                             |
|              | min_mandatory_commission_rate     |              0.1 | 10%，节点最低佣金费率                                        |

