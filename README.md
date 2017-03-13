使用AndroidStudio一阵子了，近来需要开发javaEE程序，再次使用eclipse，快捷键什么的感觉很不惬意，于是乎，
整理一下ItelliJ IDEA，用IDEA创建第一个Web项目。

1、new project
选择文件中new project 出现如下的界面：
![new project](/Picture/1.png)

2、填写project name

![project name](/Picture/2.png)



选择File中的New Module创建项目，选择图中标记的项点next继续下一步

点击Finish之后会自动创建一个项目名为WebTest，目录结构如图所示：

双击打开index.jsp文件，作适当的修改。


接下来的任务就是将项目部署到Tomcat服务器
在界面的右侧上方有个下拉框，这个地方下拉会发现有一个Edit Configuration选项


打开出现下面的界面


在Default下面有一个TomcatServer进行Tomcat的基本配置


然后回到这个弹出框的上面，部署项目





服务器部分配置完成




这样就已经成功了。

到了这里再补充一个问题

这里我的是成功了的，但是在之前用的时候总是遇到一个问题，自动弹出这个访问页面之后一直都是404 Not Found ，我遇到这个问题是因为我多个项目同时部署到一个Tomcat上，导致8080端口被占用，控制台报了异常信息
TOMCAT异常 Socket bind failed: [730048]

但是我只看到了最后的部署完成的信息，没看到上面的异常提示，所以一度卡在这里。

这个问题怎么解决呢？


输入netstat -ano | findstr 8080;查看占用端口8080


输入taskkill /f /pid 占用进程；关闭占用进程

然后重新运行就可以了。

补充一点：
多个项目可以通过如下的方式进行部署。
