## itop FAQ ���������б�

### �ٷ�Wiki������Ҫ��ǽ��

https://wiki.openitop.org/
��������ϸ���ĵ�����

���磬����api���ж��ο���

    https://wiki.openitop.org/doku.php?id=2_3_0:advancedtopics:rest_json&s[]=api

���Զ���itop

    https://wiki.openitop.org/doku.php?id=2_3_0:customization:start

��չ�������
  
    https://wiki.openitop.org/doku.php?id=extensions:start

[����...](https://wiki.openitop.org)

### ���Զ���itop����

�����Լ�����İ汾�����ڷŵ�����ĵ���

[���Զ���itop����](���Ի�����.md)

### itop������̳��qqȺ

ITIL��itopʵʩ������̳ http://www.itilxf.com/

qqȺ 233051696

### itop���������ĵ� 

    http://itop.doc.hardie.me/

### itop �ʼ�����

/conf/production/config-itop.php ��Ϊ��Ĭ��Ϊֻ�����޸�Ϊ��д����������ֻ����210�汾�����ֱ�Ӻ�̨���ã�
 
����email_transport  �޸�'email_transport' => 'PHPMail'Ϊ��ע��qq������Ҫȥqq web���������Ȩsmtp���ʣ���Ȩʱ�������һ������
һ�����õ�����Ϊ��Ȩsmtp����ʱ�����õ��棩�� 

	  'email_transport' => 'SMTP',
	  'email_transport_smtp.host' => 'smtp.qq.com',
	  'email_transport_smtp.password' => 'sbmht',
	  'email_transport_smtp.username' => '1000@qq.com',
    'forgot_password_from' => '1000@qq.com',

����smtp�����ļ������봫�䣬���ױ��˼������ݣ�����ȫ��ͬ��ĳЩ��Ӫ������������ǽ�ֹ25�˿ڣ�����ͨsmtpЭ��������Ͳ����ʼ�
�����Ƽ�ʹ��ssl/tls֤����ܵ��ʼ�������Э���������£�

        'email_transport_smtp.encryption'=> 'tls',
        'email_transport_smtp.port ' => 465,
        'email_transport_smtp.host' => 'smtp.qq.com',
        'email_transport_smtp.password' => 'sbmht',
        'email_transport_smtp.username' => '1000@qq.com',
        'forgot_password_from' => '1000@qq.com',


### ���뵼����������

�޸������ļ��� /conf/production/config-itop.php��������ͨ����̨`������-����`�޸�

     'csv_file_default_charset' => 'ISO-8859-1',

�޸�Ϊ

    'csv_file_default_charset' => 'UTF-8',

Ȼ���������̱�֤�ļ����붼��utf8.

### ʱ�䲻�ԣ���7��Сʱ

itopĬ��Ϊ����ʱ�䣬�ͱ���ʱ���7��Сʱ���޸������ļ���/conf/production/config-itop.php����
����ͨ����̨`������-����`�޸�

    'timezone' => 'Europe/Paris',

�޸�Ϊ
 
    'timezone' => 'Asia/Shanghai',



###  ������ģ��

���� 

    itop@xxx.com     

�ظ���     

�ռ��� 

    SELECT Person WHERE id= :this->contactid

���� 
 
    SELECT Person JOIN lnkPersonToTeam AS T ON T.person_id = Person.id WHERE T.team_id = :this->manager_group_id

����    

���� 

     ���iTop �˻���Ϣ     

�ʼ��� 

     <pre>$this->first_name$ $this->last_name$���</pre> 

     <pre>���iTop�˻�������</pre> 
     <pre>iTop ��¼��ַ��</pre> 
     <pre>http://ip/pages/UI.php</pre> 

     <pre>����û���Ϊ��$this->login$</pre> 

     <pre>�û�����Ϊ:xxx</pre> 

     <pre>���¼��������룡���ʼ�Ϊϵͳ�Զ��ʼ�������ظ����κ������뽨������ϵxxx</pre> 

     <pre>xxx��˾iTop</pre> 

### ����2.4�汾����

���°汾��û�к��������ٷ������ļ���������֮ǰ�ģ����ز�ȫ��������[2.34�汾�����ļ�ѹ����](zh-cn.dict.php.zip)
��ѹ�����°�װ��2.4�汾���ļ������ɡ���Ҫ���ǵ��ļ��ǣ�ע�ⱸ�ݣ���

    env-production\dictionaries\zh-cn.dict.php

### profile ��ɫ�û���������

ֱ���޸ı� priv_urp_profiles

���`priv_urp_profiles`���б�����

    TRUNCATE `itop_priv_urp_profiles`; 

ִ������SQL���ɺ��������ݣ�

    INSERT INTO `itop_priv_urp_profiles` (`id`, `name`, `description`) VALUES
     (1, 'Administrator', '���Բ������Ʋ����κζ���'),
     (2, 'Portal user', '���øý�ɫ���˺ţ����ܷ��ʳ��Ż�֮����������ܣ����еķ��ʽ������¶����Ż�����'),
     (3, 'Configuration Manager', '��������ܿ�������������ĵ�������'),
     (4, 'Service Desk Agent', '���𴴽��¼�����'),
     (5, 'Support Agent', '��������ͽ������'),
     (6, 'Problem Manager', '�����ͽ����ǰ�������'),
     (7, 'Change Implementor', '����ִ�б��'),
     (8, 'Change Supervisor', '�����ر����������������'),
     (9, 'Change Approver', '�����������'),
     (10, 'Service Manager', '������񽻸����ͻ�(�ڲ�)'),
     (11, 'Document author', '�����ĵ���д'),
     (12, 'Portal power user', '������������ɫ�Ļ����ϣ�����ͨ���Ż����������е��¼���');


### ��LNMPһ����װ����װitop 2.3.4ʱ��װ���ϵ�����

�����Ų鷢����Ҫ�ǰ�װ�����ڻ�ȡϵͳ·��ʱ��ʹ��_SERVER[��SERVER_NAME��]���������ú�����ȡ���ǵ�ʱ
ϵͳweb��������nginx����server_name ֵ��Ĭ������Ϊ_�������°�װ��������js�ļ������������أ����԰�װ
�����ܻ�ȡ������õĲ��������°�װ���ɹ������������

1���޸���ػ�ȡ·����php�ļ���������Ҫ��php���ڴ˺��ԣ���

2���޸�nginx�����ļ���/usr/local/nginx/conf/nginx.conf��server_nameֵ��

    server_name _; �޸�Ϊ server_name IP;

IPΪ�����������ip��ַ��Ȼ���ؼ���nginx���ü���
  
     /usr/local/nginx/sbin/nginx -s reload

### ���ؿ��Դ򿪣��������������򲻿��������ܴ򿪣�������ʽ��ͼƬ���ز�������

  ��Ҫ��`app_root_url`�������������⡣

      �� 'app_root_url' => 'http://localhost/itop/', 
      ����  'app_root_url' => 'http://127.0.0.1/itop/', 

  �޸�Ϊ

      'app_root_url' => '/itop/',

### �ʼ��Զ����ɹ�����

  ע�ⰲװ���ʱ��ͬ�汾��Ӧ�İ汾��ͬ�������ݣ���

  itop 2.02��ǰ�汾��Ӧ�� [ticket-from-email 2.2](https://wiki.openitop.org/doku.php?id=extensions:ticket-from-email_2_2)
                                                  
  itop 2.02�Ժ�itop2.2 �汾��Ӧ�� [ticket-from-email 2.6.12](https://wiki.openitop.org/doku.php?id=extensions:ticket-from-email_2_6)
 
  itop 2.3�Ժ�汾��[ticket-from-email 3.0.5](https://wiki.openitop.org/doku.php?id=extensions:ticket-from-email)
    
  ���а�װ���̣��������3.0�汾�������ļ��ж�Ӧ��װ�����������װ���ڹ������и��ռ��书�ܲ˵���
ͨ���������ں�̨���������������ݣ��ܷ��㣬����ʹ�á���֮ǰ�汾ֻ��Ӧ��װһ�������û�����ò˵���
ֻ��ͨ�������ļ��ֶ����á�

### `graphviz`������ͼ������

  `graphviz` do not found(executable path: /usr/bin/dot)��

  itop��CI���Ը������õ�������Ӱ���ϵ�Զ���������ͼ������ͼ������Ҫ����`graphviz`��������ɣ�`graphviz`���ϵͳû�еĻ���Ҫ��װ��
֧��linux��windows�İ�װ��linux�°�װ�����ð��������������Centos������`yum install graphviz`����װ��ΪĬ�ϵ�/usr/bin/dot�¡������
window�º�linux���밲װ�Ļ�����������Ŀ¼����ʱ�����Ҫ����dot����·�����������ϵͳ��װ�����ã����߰�װ�ú��������ļ����ã����磺

    'graphviz_path' => 'C:\\Program Files\\Graphviz\\bin\\dot.exe',

### �������⣬����������...



## License

Licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0.html).



