云计算技术综述
=============

## 整体思路

**第一节：引言**

技术探索期 -> 技术落地期 -> 开始应用繁荣期，即云计算从 machine-oriented 过渡到了 Application-oriented

**第二节：云计算历史的简单回顾**

主线是：硬件资源虚拟化、池化 -> 软件定义的数据中心，更好地管理资源 -> 数据中心操作系统，更好地支撑云化应用（云操作系统：是从另一个角度描述数据中心操作系统）。

提出 云计算 由 machine-oriented 到 Application-oriented 的发展趋势，引出数据中心操作系统


**第三节 ：数据中心操作系统的研究现状**

国际研究进展

- 工业界： Google和Apache的一些进展，如Borg, Omega, Kubernetes[2,3,4], Mesos
- 学术界：待补充

国内研究进展：

- 网构软件
- 虚拟计算环境
- 透明计算
- 云际计算


*从资源角度* 

- 资源来源泛在化 ： 从管理实际物理资源 到 管理虚拟云资源（比如k8s跑在google cloud上）
- 计算方面： 计算单元 从 虚拟机为主 完成了 虚拟机、container并存的转变
- 网络架构： 从 为虚拟机提供网络服务 到 提供灵活的软件架构（软件定义网络）、为应用服务的多样化的网络服务（NFV等）
- 存储： 待补充

- 新型硬件 ： 更好地支撑云化应用

*从应用的角度* 

- 应用类型领域化 ：特定领域应用上云
- 云化应用 ： 应用的开发、部署、运行、维护都通过在云端进行，云端一体化
- 作业调度管理 ： 用户如何在数据中心上跑作业（批处理，长服务），
- 新型云环境下的编程模型 ： MapReduce等

**第四节 ：云计算研究的发展趋势**

“三化一提升”，其中“三化”是指应用领域化、资源泛在化和系统平台化，而“一提升”则指服务质量的提升。

## 现状分析

[1] 定义云计算 = Utility Computing + Service Computing, 分析了云计算面临的10
个障碍和机会, 认为云计算形态主要是公有云，私有云和私有数据中心难以获得公
有云的所有好处, 提出私有云应向混合云发展, 提出突发计算(Surge Computing)的概念。

[2,3,4] 介绍了Google近10年在数据中心容器管理方面的3个主要系统，以及Google从中获得的一些经验

- Container作为资源管理和应用封装单元，和application是一一对应的，为云化应用架构带来了很多变化，促使数据中心基础设施转换为Application-oriented infrastructure；多种作业混合调度，提供资源利用率；更多的网络服务来为应用服务；

> Building management APIs around containers rather than machines shifts the “primary key” of the data center from machine to application. This has many benefits: (1) it relieves application developers and operations teams from worrying about specific details of machines and operating systems; (2) it provides the infrastructure team flexibility to roll out new hardware and upgrade operating systems with minimal impact on running applications and their developers; and (3) it ties telemetry collected by the management system (e.g., metrics such as CPU and memory usage) to applications rather than machines, which dramatically improves application monitoring and introspection, especially when scale-up, machine failures, or maintenance cause application instances to move.



## 参考文献

[1] Michael Armbrust, Armando Fox, Rean Griffith, Anthony D. Joseph, Randy Katz, Andy Konwinski, Gunho Lee, David Patterson, Ariel Rabkin, Ion Stoica, and Matei Zaharia. 2010. A view of cloud computing. Commun. ACM 53, 4 (April 2010), 50-58. DOI=http://dx.doi.org/10.1145/1721654.1721672

Google的工作：

[2] Burns B, Grant B, Oppenheimer D, et al. Borg, omega, and kubernetes[J]. Communications of the ACM, 2016, 59(5): 50-57.

[3] Verma, Abhishek, et al. "Large-scale cluster management at Google with Borg." Proceedings of the Tenth European Conference on Computer Systems. ACM, 2015.

[4]Schwarzkopf, Malte, et al. "Omega: flexible, scalable schedulers for large compute clusters." Proceedings of the 8th ACM European Conference on Computer Systems. ACM, 2013.
