SessionedEurekaHttpClient，用于客户端查询(query)和注册(registration)、远程region复制(remote region replication)，基本特定为不定时重建会话，刷新间隔在初始值[0,init/2]。

RetryableEurekaHttpClient，可向多个eureka-server重试，默认3次；维护了不可用节点的集合quarantineSet。

