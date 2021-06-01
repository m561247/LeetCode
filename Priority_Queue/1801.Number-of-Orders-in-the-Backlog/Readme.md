### 1801.Number-of-Orders-in-the-Backlog

常规的模拟。设置两个PQ，分别放置待卖的订单和待买的订单，前者按价格从低到高排序，后者按价格从高到低排序。

对于任何新订单，如果是买入，则取待卖队列的队首去匹配；如果是卖出，则取待买队列的队首去匹配。匹配之后如果新的买入订单有剩余，则加入待买队列；如果新的卖出订单有剩余，则加入待卖队列。反之，匹配之后如果原待卖订单有剩余，则更新amount之后放回待卖队列；匹配之后如果原待买订单有剩余，则更新amount之后放回待买队列。