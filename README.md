项目基于Springboot框架及SSM原理，整合多类功能插件，设计开发了一款体育赛事社交平台，实现的基本功能包括注册登录、发布帖子、搜索帖子、评论、关注、系统消息、热帖排行等。
技术栈：SpringBoot、Spring、Spring MVC、MyBatis、Redis、Kafka、Elasticsearch、Caffeine
•平台为用户账号安全做出一系列防护的措施，针对用户密码加密，并整合 Kaptcha 配置登录时的验证码，并整合了SpringEmail系统自动发送激活邮件并帮助用户激活，确保了每个账号的安全性和有效性。
•配置Interceptor拦截器+自定义元注解拦截未登录请求，防止外界URL恶意获取用户的隐私。
•针对访问频率高、对性能要求高的功能，如点赞、评论、关注等，整合了性能较好的Kafka搭建MQ系统，每当对应事件触发时，消费者会自动异步消费处理，大幅度提高了平台的响应速度。
•增加了帖子的搜索模块，整合了性能较优的Elasticsearch搜索引擎，实现对全站帖子关键词的搜索。
•为提高总体的性能，采用本地缓存Caffeine及分布式缓存Redis，Caffeine中主要存放热帖排行，大幅度提高CPU吞吐量，Redis中存放点赞评论等数据量大的数据，大大增加读写效率。

9.  用 https://cdn.bootcss.com/twitter-bootstrap/4.3.1/css/bootstrap.min.css替换html文件中的https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css
10.spring.mail.username=修改
spring.mail.password=修改
11.数据库密码修改
12.<a class="page-link" th:href="@{__${page.path}__ (current=${page.current}-1)}">上一页</a>
13<script src="https://cdn.jsdelivr.net/npm/bootstrap@4.3.1/dist/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>替换src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" crossorigin="anonymous"></script>
14.<script src="https://unpkg.com/bs-custom-file-input/dist/bs-custom-file-input.js" crossorigin="anonymous"></script>   替换
15.启动kafka服务器：如果锁死，把日志删除
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
.\bin\windows\kafka-server-start.bat .\config\server.properties
16.启动elasticsearch   bin/elasticsearch.bat
17.修改wk文件
