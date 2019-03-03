
#相关文档:
https://blog.csdn.net/zxr1521904712/article/details/51165474

#1.
~~~
首先我们来创建一个java项目Tomcat，创建一个Servlet.MyServletIn接口，添加一个service方法，以模拟servlet中的service方法。
~~~
#2.
~~~
将我们的Servlet.MyServletIn接口导出为ServletPkg.jar文件作为我们的servlet库。
~~~
#3.
~~~
在项目根目录下添加TomcatConf.txt文件作为Tomcat的配置文件，这里简单起见采用普通文本而非Xml文件，此文件中存放两行内容 ，第一行所要部署servlet项目目录，第二行你自己的真实Servlet类名(包含包路径)。
~~~
#4.
~~~
创建一个Core.TomcatCore类，并在其中添加main，作为整个容器的入口，在main中完成初始化tomcat本身、通过TomcatConf.txt配置文件下的servlet文件系统路径及类包路径信息，加载所部署servlet等工作。
~~~
#5.
~~~
另创建一个java项目MyWeb(此项目不需要main，用来模拟我们的web项目，当然这里只有servlet而已。)
~~~
#6.
~~~
将我们的”Servlet库“ServletPkg.jar导入我们的”Web项目“。
~~~
#7.
~~~
在MyWeb中添加一个实现了MyServletIn接口的类MyServlet。
~~~
#8.
~~~
实现MyServlet的抽象方法service模仿真实Servlet的行为。
~~~
#9.
~~~
部署我们的"web项目“到我们的Tomcat，即将我们的"web项目"根下的bin路径写入Tomcat根下的配置文件(TomcatConf.txt)的第一行，并将我们的Servlet类名写入配置文件第二行。如下:
~~~



    

