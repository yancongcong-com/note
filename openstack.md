# openstack

存储可分两类

临时存储

持久性存储：块存储，对象存储和文件系统存储

临时存储 运行操作系统和提供启动空间    通过文件系统访问  虚拟机 Nova 虚拟机终止

cinder 块存储 为虚拟机添加额外的持久化存储

swift 对象存储  存储海量数据，包括虚拟机镜像

 manila  文件存储     操作系统为虚拟机添加额外的持久化存储

cinder架构部署：以SAN存储为例

Cinder-api,CInder-Scheduler,Cinder-Volume可以选择部署到一个节点上，也可以分别部署

API采用AA模式

scheduler负载均衡，横向扩展     节点分发任务  收取上报能力                    预留资源从保证数据一致性

RabbitMQ,主备或集群

mysql支持主备或集群

api组件 卷  快照  卷（attach/detach）   其他(Volume  type  Quotas  Backups)

scheduler	列出所有后端   根据后端的能力进行筛选   根据权重给后端排序  返回最合适的后端

Volume多节点部署，使用不同的配置文件，接入文件不同的后端设备，由各存储厂商Driver代码与设备交互，完成设备容量和能力信息和能力信息





























































