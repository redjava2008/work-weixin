# work-weixin
企业微信开发

# 项目描述
本项目是基于企业微信的开发


# 版本介绍
v1.0.0. 基于开源项目 https://github.com/binarywang， 根据自身的企业微信的信息，进行一个配置 和 简单的消息配置。


# 版本难点讲解
## v1.0.0
### 关于企业微信的配置信息 
1. 重新命名 将 application.yml.template 重命名为 application.yml
   文件的地址为： https://github.com/binarywang/weixin-java-cp-demo/blob/master/src/main/resources/application.yml.template
   注意：这里的配置文件 有 多实例配置 和 单实例配置， 项目默认使用的是 多实例配置

2. 修改 重命名后的 application.yml 文件，这里的配置信息，需要结合你的企业微信里面的信息（登录企业微信https://work.weixin.qq.com/wework_admin/frame#apps）（如果企业微信里面没有应用，需要自行新建）。
   具体修改样例如下：

   获取配置信息，在企业微信的位置如下图所示：
   
   
4. 目前 将 application.yml 改为 基于 单实例配置 进行发布，需要修改的文件有以下：
   主要是springboot项目初始化，自动加载的@Configuration，@ConfigurationProperties，@EnableConfigurationProperties
   需要将 mutil 目录下面 所有 *.java 的 自动加载标签注释（加上注释，使其不生效）
   https://github.com/binarywang/weixin-java-cp-demo/tree/master/src/main/java/com/github/binarywang/demo/wx/cp/config/mutil

   需要将 single 目录下面 所有 *.java 的 自动加载标签注释（删除，使其生效）
   https://github.com/binarywang/weixin-java-cp-demo/tree/master/src/main/java/com/github/binarywang/demo/wx/cp/config/single
   
