# schoolfoodreserve
Java：187 基于Springboot的校园点餐系统
> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

## 项目介绍

​

系统为顾客线上订餐提供便利。主要实现了顾客模块和管理员模块两大部分，这两大模块具体功能如下：

（1）顾客模块：

①顾客登录系统进行菜单浏览

②可以输入食材进行菜品的模糊查询

③顾客进行菜品的选择添加，对已选菜品进行数量的增减或者取消

④选择完毕后提交订单到后台并进行在线支付结账功能

⑤顾客注册成为会会员可以对自己的个人信息进行更改，例如送餐地址、联系电话、账号密码等

（2）管理员后台模块：

①管理员登录后台，可以创建管理员账号

②管理员可以对菜单进行增加、删除和修改，例如菜品的图片、价格、描述等

③管理员对提交到后台的订单进行审核管理，确定订单生成

⑥可以统计顾客消费情况并以次为依据提升顾客会员等级并进行优惠打折（这个打折力度可以由管理员定期进行调整）

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：SpringBoot + MyBatis + Vue + Bootstrap + jQuery

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)


# 运行截图

## 功能模块截图

![img](https://i-blog.csdnimg.cn/img_convert/d021b2a53ff9c38b3b7631dbb147c2e2.png)

![image20241218000458330](https://i-blog.csdnimg.cn/img_convert/58eb0d026e3bff28fa69aafc65d132f9.png)

![image20241218000549791](https://i-blog.csdnimg.cn/img_convert/cac7f51ef3413f7b4a2b4208b461d106.png)

### 项目截图

前台

![图片1](https://i-blog.csdnimg.cn/img_convert/c5e3803a51f80274147d9f2e186701a8.png)

![图片2](https://i-blog.csdnimg.cn/img_convert/5d863c156bf3737e7c94e881f5a10c9b.png)

![图片3](https://i-blog.csdnimg.cn/img_convert/ea296acd555ca1e0bfa6137f6eff3c08.png)

![图片4](https://i-blog.csdnimg.cn/img_convert/bd24cc5e7ccfcbb35708f57ad68326ca.png)

后台

![图片5](https://i-blog.csdnimg.cn/img_convert/c9eca7ac2f2fe3acc8dcf1ecce956330.png)

![图片6](https://i-blog.csdnimg.cn/img_convert/b3a4373fbcaa52a34d1e3d801046793a.png)

![图片7](https://i-blog.csdnimg.cn/img_convert/366098dc53299a4d8b077616482038f0.png)

![图片8](https://i-blog.csdnimg.cn/img_convert/5744a77018484d1bc0b922822d42a825.png)

![图片9](https://i-blog.csdnimg.cn/img_convert/97936a6e06e221d5ce9f81216e15227e.png)

![图片10](https://i-blog.csdnimg.cn/img_convert/9396d7c76c8dd7e4952cee63943b68b7.png)

### 代码

```
    @Scheduled(cron = "0 0 1 * * ?")
    @SchedulerLock(name = "SystemResource.clear", lockAtMostFor = "5s", lockAtLeastFor = "5s")
    public void clearSystemResources() {
        log.info("执行清除30天前的系统资源日志时间:{} " , LocalDateTime.now());
        long thirtyDaysMillisFromLocalDate = getThirtyDaysMillisFromLocalDate(30L);
        dashboardService.clearData(thirtyDaysMillisFromLocalDate);
    }
```
