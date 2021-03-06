# 真的一点提前设计都不需要吗？

是的，需求是不可预测的，不要基于臆想的需求提前设计。

不是的，我们需要在开工之前先取得共识。共识应该包含两部分内容：

* 我们总是要做出一个“如何分工”的决定，才能开始工作。没有完美的决定，Autonomy/Consistency/Feedback 三个方面总是有被取舍掉的方面。但是我们要对“取舍了什么”达成共识。
* 敏捷开发需要我们持续地调整，持续地去响应变化。“如何保持敏捷”同样需要计划，需要达成共识。

在实践中，我们经常盲目地采取某种架构风格，比如说微服务架构，但是并不能明确地说出这个做法是“取舍了Autonomy/Consistency/Feedback中的哪些”。既不知道是为了获得什么收益，也不知道背后的代价是什么。
然后一条路走到黑，没有反思的节点，没有项目的复盘。如果我们不承认做 Big Upfront Design 是可能的，那至少要有日常反思的计划。什么症状应该触发大家去调整业务逻辑的拆分？这些症状能不能被量化？能不能排上议程？

我们可以有一些习惯做法，这些 bias 让我们可以快速开始

* 大厂的商业那么成功，那复制他们的技术方案也会使我们商业成功
* things executed in same time, write in same git repository
* things executed in same os process, write in same git repository
* 招人那么难，相同技能的人放一起才能招募更多优秀的人

但这些 bias 不应该是盲从的终点，而是思考和试错的起点。如果选择某个切分的策略，需要想想

* Autonomy 将来怎么保证
* Feedback 将来怎么保证
* Consistency 将来怎么保证

我们不需要提前设计，但是要基于共识进行分工。这就是《业务逻辑拆分模式》主旨所在。
