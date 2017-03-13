使用AndroidStudio一阵子了，近来需要开发javaEE程序，再次使用eclipse，快捷键什么的感觉很不惬意，于是乎，
整理一下ItelliJ IDEA，尝试用IDEA创建第一个Web项目。

####1、new project
选择文件中new project 出现如下的界面：
![步骤1](/Picture/1.png)

####2、填写project name

![步骤2](/Picture/2.png)

####3、目录结构如图所示，双击打开index.jsp文件，作适当的修改。接下来的任务就是将项目部署到Tomcat服务器
在界面的右侧上方有个下拉框，这个地方下拉会发现有一个Edit Configuration选项。

![步骤3](/Picture/3.png)

####4、打开出现下面的界面

![步骤4](/Picture/4.png)

####5、在Default下面有一个TomcatServer进行Tomcat的基本配置

![步骤5](/Picture/5.png)

####6、然后再次打开这个弹出框(Run/Debug configruations)

![步骤6](/Picture/6.png)

如图步骤所示，进入部署项目界面

####7、部署项目

![步骤7](/Picture/7.png)
![步骤7](/Picture/8.png)
![步骤7](/Picture/9.png)

(说明一下，这里是可以进行多个项目的部署的。)

到这里，服务器部分配置完成，运行项目，成功出现如图所示结果

![部署成功](/Picture/10.png)

这样就已经成功了。



有时候会提示404 Not Found ，遇到这个问题可能是因为多个项目同时部署到一个Tomcat上，导致8080端口被占用，控制台报了异常信息

TOMCAT异常 Socket bind failed: [730048]，有时候甚至看不到异常。

解决步骤：
windows键+R 弹出运行窗口，输入cmd打开命令号窗口，查看8080端口被那个PID的应用程序占用了，然后打开任务管理器，
找到对应PID的进程，如果看不到PID需要进行设置，然后找到对应PID的进行，右键结束该进程，如图所示：

![解决端口占用](/Picture/11.png)
![解决端口占用](/Picture/12.png)
![解决端口占用](/Picture/13.png)

然后重新运行就可以了。

