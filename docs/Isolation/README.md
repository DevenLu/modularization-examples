# 隔离的两大场景

有很多隔离模式来加快反馈的速度，有两大场景：

* [控制变更](./ControlChange.md)：外部输入没变化，变更运行时。变更之前可以工作，变更之后不工作了，那就是变更引起的问题。
* [控制边界](./ControlBoundary.md)：运行时没变更，外部输入发生变化时出问题了。不需要知道边界里面是什么逻辑，所有人都使用统一的方式来定义边界。出了问题可以快速排除不是自己的问题。

“一致性”需求的很大来源就是为了用统一的方式来定义边界，比如都接同一套监控系统，使得分工协作的时候不需要掌握那么多门外语。

# 微服务

微服务的起源是 devops 运动。鼓励 dev 拥有自己的线上服务，dev 自己来做 ops 的工作从而减少沟通成本。
毫无疑问，微服务的合理性并不是从 Autonomy 或者 Consistency 出发，而是以 Feedback 为主要的出发点。

当一个 7*24 的互联网高并发应用稳定性成问题的时候，最合理的做法是什么？据 Google SRE 统计，线上70%的故障都是由某种变更而触发的。
控制变更的速度，尽量延长灰度发布的时间是最重要的事情。
如果变更的粒度只有进程，而进程又只有一个，势必上线的队列会过长。
此时拆分微服务就是延长灰度发布时间最有效的手段。
同时让每个 dev 直接负责线上服务的稳定性告警，可以极大加快故障的定位和处置速度。

那么是不是拆分进程一时爽，一直拆分一直爽呢？
很多过度使用微服务的分布式系统无一例外地遇到了严重的 Feedback 问题。
难道应该是强调一个业务就应该由一个团队端到端负责，重新打起 Monolith 的大旗吗？
这其实就等价于说，怎么分技术的进程，应该取决于业务部门的组织架构。
但是业务部门的组织架构也是三天两头调整的。就是技术部门想要跟着调，业务部门每调整一次，集群就完全重部署一次SRE也不会同意的。

那么怎么拆分进程才是合理的呢？为什么这么拆就是合理的呢？