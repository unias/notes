云计算技术综述
=============

## 整体思路

**第一节：引言**

云计算的定义，云计算，网格计算，Utility Computing, 服务计算的关系。



**第二节：云计算历史的简单回顾**

技术探索期 -> 技术落地期 -> 开始应用繁荣期，即云计算从 machine-oriented 过渡到了 Application-oriented

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


[5] 分析了云计算的一些最佳实践,  如：弹性体系结构(Elastic Architecture)，
设计时考虑失败（Design for Failure), 高可用，性能，安保，监控等。该文对
主要的公有云提供商如AWS, Rackspace, Google, Microsoft Azure, HP, IBM等进
行了分析比较，也对用于构建私有云的Eucalyptus, OpenStack, CloudStack, 以
及VMware等进行了分析比较。

[6] 介绍了云计算中的网络虚拟化和软件定义网络技术发展现状，认为多云环境下的
应用投递(Application delivery)是一个亟待解决的问题, 并介绍了与之相关的工
作OpenADN。

[7] 介绍了多云互联(Inter-Cloud)的技术现状和挑战。

[8] 介绍了容器技术(lxc, docker, kubernetes)以及容器技术是如何成为云计算基础设施中重要的一部分的。

[9] NIST对云计算的定义是非常有影响力的，也被广泛引用。给出了云计算的确切定义，云计算的必要特征(On-demand self-service, Broad network access, Resource pooling, Rapid elasticity, Mesasured service)，服务模型的定义(SaaS, PaaS, IaaS)，部署模型的定义(Private cloud, Community cloud, Public cloud, Hybrid cloud)。

[10] 介绍了Mesos系统。

[11] 本文研究了如何在云环境中，管理降低同一物理机上不同虚拟机的性能干扰问题。

[12] 本文研究了在数据中心中，在满足延迟型服务的基础上尽可能高吞吐量地运行Batch作业，以此来提升数据中心的资源利用率。

## 参考文献

[1] Michael Armbrust, Armando Fox, Rean Griffith, Anthony D. Joseph, Randy Katz, Andy Konwinski, Gunho Lee, David Patterson, Ariel Rabkin, Ion Stoica, and Matei Zaharia. 2010. A view of cloud computing. Commun. ACM 53, 4 (April 2010), 50-58. DOI=http://dx.doi.org/10.1145/1721654.1721672

Google的工作：

[2] Burns B, Grant B, Oppenheimer D, et al. Borg, omega, and kubernetes[J]. Communications of the ACM, 2016, 59(5): 50-57.

[3] Verma, Abhishek, et al. "Large-scale cluster management at Google with Borg." Proceedings of the Tenth European Conference on Computer Systems. ACM, 2015.

[4] Schwarzkopf, Malte, et al. "Omega: flexible, scalable schedulers for large compute clusters." Proceedings of the 8th ACM European Conference on Computer Systems. ACM, 2013.

[5] N. Serrano, G. Gallardo and J. Hernantes, "Infrastructure as a Service and Cloud Technologies," in IEEE Software, vol. 32, no. 2, pp. 30-36, Mar.-Apr. 2015.
doi: 10.1109/MS.2015.43

[6] R. Jain and S. Paul, "Network virtualization and software defined networking for cloud computing: a survey," in IEEE Communications Magazine, vol. 51, no. 11, pp. 24-31, November 2013.  doi: 10.1109/MCOM.2013.6658648

[7] Toosi A N, Calheiros R N, Buyya R. Interconnected cloud computing environments: Challenges, taxonomy, and survey[J]. ACM Computing Surveys (CSUR), 2014, 47(1): 7.

[8] Bernstein D. Containers and cloud: From lxc to docker to kubernetes[J]. IEEE Cloud Computing, 2014, 1(3): 81-84.

[9] Mell P, Grance T. The NIST definition of cloud computing[J]. 2011.

[10] Hindman B, Konwinski A, Zaharia M, et al. Mesos: A Platform for Fine-Grained Resource Sharing in the Data Center[C]//NSDI. 2011, 11(2011): 22-22.

[11] Novakovic, Dejan M., et al. "DeepDive: Transparently Identifying and Managing Performance Interference in Virtualized Environments." USENIX Annual Technical Conference. 2013.

[12] Lo, David, et al. "Heracles: improving resource efficiency at scale." ACM SIGARCH Computer Architecture News. Vol. 43. No. 3. ACM, 2015.
