## itop FAQ 常见问题列表

### 官方Wiki（不需要翻墙）

https://wiki.openitop.org/
里面有详细的文档介绍

比如，调用api进行二次开放

    https://wiki.openitop.org/doku.php?id=2_3_0:advancedtopics:rest_json&s[]=api

个性定制itop

    https://wiki.openitop.org/doku.php?id=2_3_0:customization:start

插件下载
  
    https://wiki.openitop.org/doku.php?id=extensions:start

[更多...](https://wiki.openitop.org)

### 个性定制itop中文

笔者自己翻译的版本，现在放到这个文档中

[个性定制itop中文](个性化定制.md)

### itop中文论坛和qq群

ITIL和itop实施中文论坛 http://www.itilxf.com/

qq群 233051696

### itop在线中文文档 

    http://itop.doc.hardie.me/

### itop 邮件配置


      /conf/production/config-itop.php 改为（默认为只读，修改为可写，操作完后改只读，210版本后可以直接后台配置）
 
        查找email_transport  修改'email_transport' => 'PHPMail'为： 

	'email_transport' => 'SMTP',

	'email_transport_smtp.host' => 'smtp.qq.com',
	'email_transport_smtp.password' => 'sbmht',

	'email_transport_smtp.username' => '1000@qq.com',

        'forgot_password_from' => '1000@qq.com',

### 导入导出数据乱码

修改配置文件（ /conf/production/config-itop.php），或者通过后台`管理工具-配置`修改

     'csv_file_default_charset' => 'ISO-8859-1',

修改为

    'csv_file_default_charset' => 'UTF-8',

然后整个过程保证文件编码都是utf8.

### 时间不对，差7个小时

itop默认为巴黎时间，和北京时间插7个小时，修改配置文件（/conf/production/config-itop.php），
或者通过后台`管理工具-配置`修改

    'timezone' => 'Europe/Paris',

修改为
 
    'timezone' => 'Asia/Shanghai',



###  触发器模版

来自 

    itop@xxx.com     

回复到     

收件人 

    SELECT Person WHERE id= :this->contactid

抄送 
 
    SELECT Person JOIN lnkPersonToTeam AS T ON T.person_id = Person.id WHERE T.team_id = :this->manager_group_id

隐送    

主题 

     你的iTop 账户信息     

邮件体 

     <pre>$this->first_name$ $this->last_name$你好</pre> 

     <pre>你的iTop账户被创建</pre> 
     <pre>iTop 登录地址：</pre> 
     <pre>http://ip/pages/UI.php</pre> 

     <pre>你的用户名为：$this->login$</pre> 

     <pre>用户密码为:xxx</pre> 

     <pre>请登录后更改密码！本邮件为系统自动邮件，请勿回复，任何问题与建议请联系xxx</pre> 

     <pre>xxx公司iTop</pre> 

### 最新2.4版本汉化

最新版本还没有汉化包，官方汉化文件还是老早之前的，严重不全，可以用[2.34版本汉化文件压缩包](zh-cn.dict.php.zip)
解压覆盖新安装的2.4版本的文件，即可。需要覆盖的文件是（注意备份）：

    env-production\dictionaries\zh-cn.dict.php

### profile 角色用户描述翻译

直接修改表 priv_urp_profiles

清空`priv_urp_profiles`现有表数据

    TRUNCATE `itop_priv_urp_profiles`; 

执行以下SQL生成汉化的数据：

    INSERT INTO `yst_priv_urp_profiles` (`id`, `name`, `description`) VALUES
     (1, '超级管理员', '可以不受限制操作任何对象'),
     (2, '普通用户', '配置该角色的账号，不能访问除门户之外的其他功能，所有的访问将被重新定向到门户界面'),
     (3, '配置管理经理', '负责对已受控制配置项进行文档化管理'),
     (4, '服务台', '负责创建事件报告'),
     (5, '现场工程师', '负责分析和解决问题'),
     (6, '问题管理经理', '分析和解决当前问题的人'),
     (7, '变更工程师', '负责执行变更'),
     (8, '变更管理主管', '负责监控变更的整个生命周期'),
     (9, '变更管理经理', '负责审批变更'),
     (10, '事件管理经理', '负责服务交付给客户(内部)'),
     (11, '文档作者', '负责文档编写'),
     (12, '高级用户', '在授予其他角色的基础上，可以通过门户来访问所有的事件单');


### 用LNMP一键安装包安装itop 2.3.4时候安装不上的问题

经过排查发现主要是安装程序在获取系统路径时候使用_SERVER[“SERVER_NAME”]函数，而该函数获取的是当时
系统web服务器（nginx）的server_name 值（默认设置为_），导致安装程序的相关js文件不能正常加载，所以安装
程序不能获取相关配置的参数，导致安装不成功。解决方法：

1、修改相关获取路径的php文件（方法需要懂php，在此忽略）。

2、修改nginx配置文件，/usr/local/nginx/conf/nginx.conf的server_name值：

    server_name _; 修改为 server_name IP;

IP为你服务器所在ip地址。然后重加载nginx配置即可
  
     /usr/local/nginx/sbin/nginx -s reload

### 本地可以打开，但是其他机器打不开，或者能打开，但是样式和图片加载不出来。

  主要是`app_root_url`参数设置有问题。

      将 'app_root_url' => 'http://localhost/itop/', 
      或者  'app_root_url' => 'http://127.0.0.1/itop/', 

  修改为

      'app_root_url' => '/itop/',

### 邮件自动生成工单：

  注意安装插件时候不同版本对应的版本不同（不兼容）：

  itop 2.02以前版本对应的 [ticket-from-email 2.2](https://wiki.openitop.org/doku.php?id=extensions:ticket-from-email_2_2)
                                                  
  itop 2.02以后到itop2.2 版本对应的 [ticket-from-email 2.6.12](https://wiki.openitop.org/doku.php?id=extensions:ticket-from-email_2_6)
 
  itop 2.3以后版本用[ticket-from-email 3.0.5](https://wiki.openitop.org/doku.php?id=extensions:ticket-from-email)
    
  其中安装过程，插件包中3.0版本中两个文件夹对应安装连个插件，安装后在管理工具有个收件箱功能菜单，
通过他可以在后台配置邮箱等相关数据，很方便，建议使用。而之前版本只对应安装一个插件，没有配置菜单，
只能通过配置文件手动配置。

### `graphviz`和生成图的问题

  `graphviz` do not found(executable path: /usr/bin/dot)。

  itop的CI可以根据配置的依赖和影响关系自动生成拓扑图。但是图形生成要依赖`graphviz`软件来生成，`graphviz`如果系统没有的话需要安装。
支持linux和windows的安装，linux下安装可以用包管理软件，比如Centos可以用`yum install graphviz`，安装后为默认的/usr/bin/dot下。如果是
window下和linux编译安装的话，就在其他目录，这时候就需要配置dot所在路劲。这可以在系统安装中配置，或者安装好后再配置文件设置，比如：

    'graphviz_path' => 'C:\\Program Files\\Graphviz\\bin\\dot.exe',

### 其他问题，持续增加中...



## License

Licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0.html).



