# 作为一枚程序猿，Google是一门必备技能，所以掌握科学上网姿势很重要。
*  Warning：诸事以国家利益为重！

#####  本文推荐的科学上网方式为基于shadowsocks协议的加密上网方式。数据转发流程：你的设备<---->中间层服务器(切记在外网)<---->你要访问的服务器。因此，要点有二：
######  1、你设备上的支持Shadowsocks协议的终端软件。（iOS、Android、Mac、Windows各平台都有很多，我这就推荐一款“Shadowsocks”）。  
######  2、在外网的中间层服务器。（阿里云、AWS等，此处推荐AWS的免费服务器，视本文的加星情况再决定是否补充“如何申请AWS免费服务器”吧）。

#####  言归正传，开始搞起。
#####  一、在Ubuntu系统的中间层服务器安装Shadowsocks服务。
######  1、ssh [username]@[IP adress]                  
######  远程登录上你的中间层服务器，这一步会输入你设置的服务器密码。注：下文需要你动态填写的参数，我都会用[xxx]的形式表示。如，[useranme] 、[IP adress]等。
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
######  
######  
######  
######  
######  
######  
######  
######  
######  
######  

