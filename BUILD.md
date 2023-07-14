java: 程序包sun.nio.ch不存在
sun.util.locale.BaseLocale.SEP不存在

变更jdk版本: 11
1. RocketMq的pom.xml
2. File | Settings | Build, Execution, Deployment | Compiler | Java Compiler
3. File | Project Structure...

Idea 如何添加编译参数
File | Settings | Build, Execution, Deployment | Compiler | Java Compiler | JavaC Options | Override compiler parameters per-module
添加:
rocketmq-common: --add-exports java.base/sun.nio.ch=ALL-UNNAMED
rocketmq-store: --add-exports java.base/sun.nio.ch=ALL-UNNAMED
rocketmq-test: --add-exports java.base/sun.util.locale=ALL-UNNAMED

运行: NamesrvStartup
org.apache.rocketmq.namesrv.NamesrvStartup
Edit Configurations..
添加 Program arguments
-n 192.168.1.128:9876

运行: BrokerStartup
org.apache.rocketmq.broker.BrokerStartup
Edit Configurations..
添加 Program arguments
-n 192.168.1.128:9876 -c D:\Work\Code\Learn\rocketmq\broker\src\main\resources\conf\broker.conf autoCreateTopicEnable=true

从 源码目录 distribution 目录中的 broker.conf拷贝