# SFIP-初衷:模仿、赞同、继承
## 模仿
<pre>    模仿“微服务相关的两个关键理念：支持独立性，支持快速演化”
    SFIP将一个服务功能划分成多个更小的bean组分布在同一进程但相对独立的spring容器中,有利于更好的团队分组分工，并且有很强的可替换性。</pre>
## 赞同
<pre>    赞同分布式计算第一定律：“如果不是真正需要就不要让系统分布式”
    比如逻辑层和访问数据代理层的分布，就会让简单树状关系变成复杂网状关系。
    SFIP要将星状调用简化为树状态调用</pre>
## 继承
    继承ESB,ESB有其历史贡献,比如服务编排，快速开发
## 使用 
### 一、创建模块
服务JAVA项目构建(这里以命令行为例，eclipse等环境更方便):
```
mvn  archetype:generate -DarchetypeGroupId=com.github.yihaijun -DarchetypeArtifactId=sfip-app-archetype -DarchetypeVersion=1.0.6 -DgroupId=priv.yhj.test -DartifactId=app-test -Dversion=1.0.1 -DinteractiveMode=false -DarchetypeCatalog=local -X -e
```
<pre>然后cd app-test(进到你的artifactId对应目录)mvn install
就可以看到target目录下有了app-test-1.0.1.zip</pre>
### 二、填加业务配置和代码
模块间调用spring配置举例:
```
<sfip:callOtherAppBean id="collectorConfigChangeNotificationService"
appName="eagle-app-oap*" beanName="collectorConfigChangeNotificationServiceImpl"
interface="com.bestpay.eagle.common.service.CollectorConfigChangeNotificationService" />
```
### 三、部署模块
上传上述zip文件到sfip-standalone-1.0.6/apps 目录即可

## 附录
### 附一:sfip装启停查
<pre>
装:https://pan.baidu.com/s/1smauLBn  密码：ispl下载,unzip即可
启:sfip-standalone-1.0.6/bin/sfipStart.sh
停:sfip-standalone-1.0.6/bin/sfipStop.sh
查:sfip-standalone-1.0.6/bin/sfipQuery.sh
</pre>
### 附二:sfip几个小特点
<pre>
1、各种小程序或脚本也可配置成服务,服务可以单独热部署
2、可动态配置调用其它外部服务的通信方式，版本
3、提供方便的服务功能和性能测试工具,故障诊断工具
4、可动态通过EXCEL表配置多个服务集成流程
5、轻量级各种引擎：易使用的流程引擎，表达式解析引擎，脚本解析引擎
6、平台自身可弹性扩展，如增加业务语言到SQL语句解析引擎转换函数
</pre>
