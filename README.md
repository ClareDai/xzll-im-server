# 蝎子莱莱爱打怪 的 IM开源项目

与im结缘是在2022年，因为此类系统有足够大的挑战性，所以我对此如痴如醉，之前做过架构以及细节方面的设计，但是一直没有落地。不落地的设计不是好设计。所以有了这个项目。
目前项目处于前期阶段，后期一点点完善并将补上架构图和我能想到的所有设计细节！

想要设计一个好的im系统，是很有难度的，本项目将尽可能达到以下几点：
- 高并发
- 高可用
- 高性能
- 稳定可靠
- 灵活好扩展
- 可观测

想要实现上边的几点，将不可避免的需要集成很多中间件或框架，如下：

## 本项目涉及到的 ***【技术】***
- **已集成**
1. SpringBoot【项目搭建】✅
1. Netty【长连接服务器】✅
1. Spring Cloud Alibaba Nacos【配置中心】✅
1. Dubbo【rpc调用，利用长连接做消息转发】✅
2. zookeeper【暂时用处只是dubbo注册，后期如果没有其他用处可能移除，让dubbo注册到nacos】
1. Redis【缓存，分布式锁】✅
1. RocketMQ【解耦、削峰】✅
1. Mybatis Plus【ORM】✅
1. Mysql【数据存储】✅
2. Spring Cloud GateWay 【网关】✅
1. Oauth2 + Spring Security 【认证&鉴权】✅
1. 在雪花算法基础上 生成含有业务信息的 msgId，长连接获取批量消息id ✅

- **待集成**

1. Sentinel 【限流】
1. docker ✅ +k8s【项目部署】
1. prometheus + grafana【服务监控】
1. SkyWalking 【链路追踪】
1. ElasticSearch【聊天记录等搜索】
1. Jmeter+python脚本【压测】
2. redis集群部署
3. elasticsearch集群部署
4. canal 数据同步 mysql同步到es
5. mysql分库分表
1. 等等

## 本项目涉及到的 ***【功能点】***
1. 登录【已实现】✅
1. 单聊【已实现】✅
1. 消息id设计 ✅
1. 服务端ack ✅
1. 群聊【准备采用写扩散模型，不再像单聊一样基于dubbo做转发，直接rocketMq广播消费 】
2. 消息送达ack【保证消息可靠不丢失】✅
3. 消息有序性【通过消息id来实现】✅
4. 消息防重
5. 消息失败重试
6. 客户端断线重连 & 服务端对客户端心跳检测 ✅
1. 撤回【单聊已实现】✅ 
1. 未读/已读ack ✅
1. 离线消息【 存储 ✅ + 状态更新 ✅ + push ✅ + pull 】
1. 最近会话
3. 音视频，位置，语音，图片消息
4. 直播
1. 等... 


其他细节待补充，完善中 ~ 。
