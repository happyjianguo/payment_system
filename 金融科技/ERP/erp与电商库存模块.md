 

外账-速达






ERP与电商库存模块的异同

	先用白话简单介绍一下什么是ERP(企业资源计划)，它是对整个企业资源（人、财、物）并提供需求计划（MRP）支撑决策的管理系统。

	很多人对ERP的认识停留在进销存管理系统的概念上，其实在供应链管理中计划模才是整个业务调度的关键，而在电商场景中我们也可以看到类似ERP中计划能力的体现，比如说京东基于大数据预测对供应链的优化（商家的补货、仓库间的商品调拨、仓储管理等等），而ERP中计划也是以解决供/需平衡为基础发展起来的（比如以销定产按订单模式，按库存模式，按装配模式等），当然电商是面对的销售层不涉及到生产制造，所以这块相对来说更可控一些。这里不是主题分享就不细下展开了。

1、一些概念

         库存和仓库：仓库是真正管理物理仓库存储的货物，在企业内部有个职位叫 "仓管" ，比如他的职责就是接收采购入库，销售出库，仓库之间的转移、产线上的发料等。  而库存系统是基于仓库之上满足各类业务需求管理的模块(比如说虚拟库存等）。 比如在电商场景中商家对仓库中产品进行上架,下架，各种销售控制等。严格的说电商这块设计上应该包含：销售层、调度层、仓库层。在业务场景上电商因为是面对销售层的，很多开源电商软件只做了销售层这一块。 而在ERP中库存模块分为四大块：基础设置，库存计划，物料调拨，仓库管理。前两项功能远远大于三四项，而国内进销存软件的库存模块往往是从仓库这个角度去看待的，所以只做了仓库管理这一块，而ERP如前面所说计划能力才是关键。

2、 入库出库
          ERP入库：供应商（采购接收），客户（退货），车间（半成品入库、废料入库等），库存（库存间转移），账户（杂项入库）。
         电商入库：商家（盘点调库），商家（采购补货），客户（订单逆向流程退货），客户（售后换货）
          ERP 出库： 供应商（退货），客户（销售发放），车间（发料），库存（库存间转移），账户（杂项出库）
          电商出库： 商家（盘点调库），客户（订单正向流程销售发放），客户（售后换货）

3、关于库存扣减：
        ERP中的所有库存移动（采购接收，销售发放，库存间移动，杂项等等）都是通过库存事务处理来完成，并且以会计科目为核心汇总所有事务类型的会计信息导入到总账系统。并且从技术角度提供了事务处理接口可以方便开发人员对接。提外话：ERP中所有主模块核心都提供了接口，这样可以站在这个通用平台上开发各类业务模块的对接（比如财务接口（发票，总账……），库存接口等等）。
      电商中的库存由于不涉及到成本这块，更多是面向用户端销售的虚拟库存，所以这块一般专注在高并发情况下对库存的操作，业务上常用扣减手段是先预占的方式（锁定库存，可用库存，在途库存等等）。

4、一些技术：
         ERP属于典型的中心化业务管理不存在高并发情况，一般统过系统全局的并发管理器来处理,而电商场景中对高并发使用组合手段较多(比如限流，熔断，降级、缓存 等)。
     在高可用/高可靠上，企业级ERP的做法一般是HA来做高可用，同时运维这块也有冷备（需停机）、热备（例如rman)，远程容灾之类的，而电商这一块也有类似的手段（例如mysql的多主多从），保证高可用的核心准则是冗余方法，在各个服务层级（站点层，服务层，缓存层，数据层等等）增加冗余保证高可用。









	用友U8+承载了用友人十余年来为成长型企业的信息化管理所倾注的心血，它以U8财务业务一体化、U8 ERP、U8 All-in-One、U8+形象伴随中国经济的高速发展一路走来，见证了成长型企业信息化从7个应用模块到126个产品及行业应用、从简单管理到粗放管理到[精细管理](https://baike.baidu.com/item/%E7%B2%BE%E7%BB%86%E7%AE%A1%E7%90%86)、从部门级应用到企业级应用到供应链级应用、从局部到集成到全面到软件及[云应用](https://baike.baidu.com/item/%E4%BA%91%E5%BA%94%E7%94%A8)、从少数人应用到全员应用、从中国走向亚太走向世界的发展历程。

- 中文名 用友U8
- 全    称 用友U8企业应用套件

- 产品最新版本 V12.0

- 性    质 管理营销平台

  	 作为中国最佳经营管理平台，用友ERP—U8传承“精细管理 敏捷经营”设计理念，符合“效用、风险、成本”客户价值标准，代表了“标准、行业、个性”的成功应用模式。[2][ ]() *　　*

## 产品中心

	U8 All-in-One，为成长型企业提供全面信息化解决方案（营销、服务、设计、制造、供应、人力、办公、财务于一体），助力企业敏捷应对市场变化。
　　多渠道营销平台，线上线下并举，构建最佳营销平台，提升品牌影响力。
　　客户关系管理，以客户为中心的营销服务管理，精准把握客户需求，创造客户价值，提高客户服务水平。
　　全新的交互体验，人性化的界面交互、贴心的业务导航、实时的业务协同让用户操作更简洁，沟通更便捷。
　　移动应用，随时随地的客户管理、营销服务，及时的业务协同与审批，轻松掌控经营动态，让管理无处不在。
　　软硬一体化，整合软硬件IT解决方案，让部署更方便，让管理更精细，让运行更高效。
　　全面开放的服务体系，更丰富更专业的服务产品，自助式实施导航，开放的[开发者社区](https://baike.baidu.com/item/%E5%BC%80%E5%8F%91%E8%80%85%E7%A4%BE%E5%8C%BA)，提高IT系统运营效率，持续创造[商业价值](https://baike.baidu.com/item/%E5%95%86%E4%B8%9A%E4%BB%B7%E5%80%BC)。
　　产业链协同，设计制造协同、供应商协同、客户协同等解决方案，助力企业全面实现精细管理、产业链协同。

## 客户价值

**ERP-U8软件V8.90：**

用友ERP-U8是一套企业级的解决方案，可满足不同的制造、商务模式下，不同运营模式下的企业经营管理，U8全面集成了财务、生产制造及供应链的成熟应用，延伸客户管理至客户关系管理（[CRM](https://baike.baidu.com/item/CRM)），并对于零售、分销领域实现了全面整合。同时通过实现人力资源管理（HR），办公自动化（OA），保证行政办公事务、人力管理和业务管理的有效结合。用友ERP－U8是以集成的信息管理为基础，以规范企业运营，改善经营成果为目标，最终实现从企业日常运营、人力资源管理到办公事务处理等全方位的产品解决方案。[3][ ]()

**用友ERP-U8软件V10.0：**

U8生产制造管理是用友ERP-U8的重要组成部分，用户可以进行MRP运算、ROP运算以及车间的管理。 生产订单：是车间记载和执行生产计划和生产排程的订单性文件。它主要表示某一物料的生产数量，以及计划开工/完工日期等。[4][ ]()

**用友ERP-U8软件V10.1：**

用友ERP-U8V10.1系统为2011年12月发版的产品“用友ERP-U8 V810.1”的升级版本，包括以下行业：企业门户、财务会计、管理会计、供应链管理、生产制造、分销管理、零售管理、决策支持、人力资源管理、办公自动化、集团应用、企业应用集成。[5][ ]()

**用友ERP-U8软件V11.0**

应对成长型企业经营的一系列管理需求，U8V11.0应运而生，U8V11.0历时1年多的研发，完全符合新经济形势下成长型企业的管理需求：它为广大成长型企业提供了一个全新的应用交互体验平台，通过这个平台创新业务模式、转型升级管理、实现企业价值；提供了一个创新的营销服务管理平台，通过这个平台实现客户全生命周期管理；提供了一个商业经营平台，企业可以通过这个平台实现在线接单、交付与结算、线上业务管控；提供了一个最佳的经营管理决策平台，通过这个平台实现快速市场响应的敏捷制造、精细化的成本及费用管控、软硬一体化的条码管理、随时随地的移动应用以及深度的数据挖掘与分析；提供了一个信息化产品及服务一体化的智能的云服务平台，让客户信息化应用和管理更加畅通无阻。[6][ ]()

- 