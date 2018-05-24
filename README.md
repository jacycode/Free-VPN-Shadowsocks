# 作为一枚程序猿，Google是一门必备技能，所以掌握科学上网姿势很重要。
*  Warning：诸事以国家利益为重！

#####  本文推荐的科学上网方式为基于shadowsocks协议的加密上网方式。数据转发流程：你的设备<---->中间层服务器(切记在外网)<---->你要访问的服务器。因此，要点有二：
######  1、你设备上的支持Shadowsocks协议的终端软件。（iOS、Android、Mac、Windows各平台都有很多，我这就推荐一款“Shadowsocks”）。  
######  2、在外网的中间层服务器。（阿里云、AWS等，此处推荐AWS的免费服务器，视本文的加星情况再决定是否补充“如何申请AWS免费服务器”吧）。

#####  言归正传，开始搞起。
#####  一、在Ubuntu系统的中间层服务器安装Shadowsocks服务。
######  1、ssh [username]@[IP address]                  
######  远程登录上你的中间层服务器，这一步会输入你设置的服务器密码。注：下文需要你动态填写的参数，我都会用[xxx]的形式表示。如，[useranme] 、[IP address]等。
######  2、sudo -s
######  获取中间层服务器超级权限。注：已是超级用户请忽略，非超级用户需输入密码。
######  3、apt-get update 
######  更新Ubuntu系统的apt-get工具
######  4、apt-get install python-pip
######  通过apt-get安装python-pip工具包，以便后续安装服务。注：此步骤若出现编码类错误，请执行“export LC_ALL=en_US.utf8”后，继续安装。
######  5、pip install shadowsocks
######  通过python-pip安装Shadowsocks服务。
######  6、vi /etc/shadowsocks.json
######  此步骤用于编辑你Shadowsocks服务端配置文件。编辑内容如下：
    {    
      "server":"0.0.0.0",    
      "server_port":[port],    
      "local_address":"127.0.0.1",    
      "local_port":1080,    
      "password":[passwrod],    
      "timeout":300,    
      "method":"aes-256-cfb",    
      "fast_open":false    
    }
######  其中[port]为0~65535之间的一个数字，[password]为你客户端要连接使用的密码。记住！！！
######  7、ssserver -c /etc/shadowsocks.json -d start
######  欧了，至此你已经在中间层服务器上启动了Shadowsocks服务，可以科学上网了。
#####   二、趁你还没退出服务器，建议你安装个流量监控系统。
######  1、apt-get install vnstat
######  安装vnstat来监控相关网卡的流量，通常我们默认安装和监控的都是eth0网卡，5分钟跟新一次数据
######  2、apt-get install apache2 php7.0 php7.0-gd
######  其实通过1）就可以监控流浪数据了，接下来的这几步只是将监控数据可视化
######  3、/etc/init.d/apache2 start
######  启动apache2服务
######  4、cd /var/www/html
######  进入apache2网页容器根路径
######  5、wget http://www.sqweek.com/sqweek/files/vnstat_php_frontend-1.5.1.tar.gz
######  下载可视化项目（php版）
######  6、tar -xvf vnstat_php_frontend-1.5.1.tar.gz 
######  解压可视化项目，解压后你就可以通过http://[IP address]:[port]/vnstat_php_frontend-1.5.1/访问流量监控页面了
######  7、apt-get install libapache2-mod-php7.0
######  如果你打开的监控页面无法解析php代码，再执行这一步！！！重启apache2即可
######  8、/etc/init.d/apache2 restart
######  这是重启命令
#####   三、Mac平台如何使用Shadowsocks服务。
######  1、安装Shadowsocks软件。
######  2、打开软件，填写如下参数：
![image](https://raw.githubusercontent.com/jacycode/Free-VPN-Shadowsocks-/master/mac.png)
######  address为你的中间层服务器的公网IP地址；对应的port为第一大步、第6小步的port；password为第一大步、第6小步的password。点击OK就可以在起飞了。
######  
######  
######  
######  
######  
######  
######  
######  
######  有不明白的地方，可以微博私信我：buildrun。
######  有用的朋友们，记得加个星。

