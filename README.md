## itop FAQ ���������б�

### �ٷ�Wiki������Ҫ��ǽ��

https://wiki.openitop.org/
��������ϸ���ĵ�����

���磬����api���ж��ο���

    https://wiki.openitop.org/doku.php?id=2_3_0:advancedtopics:rest_json&s[]=api

���Զ���itop

    https://wiki.openitop.org/doku.php?id=2_3_0:customization:start

����...

### itop������̳��qqȺ

ITIL��itopʵʩ������̳ http://www.itilxf.com/

qqȺ 233051696

### itop���������ĵ� 

    http://itop.doc.hardie.me/

### itop �ʼ�����


      /conf/production/config-itop.php ��Ϊ��Ĭ��Ϊֻ�����޸�Ϊ��д����������ֻ����210�汾�����ֱ�Ӻ�̨���ã�
 
        ����email_transport  �޸�'email_transport' => 'PHPMail'Ϊ�� 

	'email_transport' => 'SMTP',

	'email_transport_smtp.host' => 'smtp.qq.com',
	'email_transport_smtp.password' => 'sbmht',

	'email_transport_smtp.username' => '1000@qq.com',

        'forgot_password_from' => '1000@qq.com',

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

### profile ��ɫ�û���������

ֱ���޸ı� priv_urp_profiles

### ��LNMPһ����װ����װitop 2.3.4ʱ��װ���ϵ�����

�����Ų鷢����Ҫ�ǰ�װ�����ڻ�ȡϵͳ·��ʱ��ʹ��_SERVER[��SERVER_NAME��]���������ú�����ȡ���ǵ�ʱ
ϵͳweb��������nginx����server_name ֵ��Ĭ������Ϊ_�������°�װ��������js�ļ������������أ����԰�װ
�����ܻ�ȡ������õĲ��������°�װ���ɹ������������

1���޸���ػ�ȡ·����php�ļ���������Ҫ��php���ڴ˺��ԣ���

2���޸�nginx�����ļ���/usr/local/nginx/conf/nginx.conf��server_nameֵ��

    server_name _; �޸�Ϊ server_name IP;

IPΪ�����������ip��ַ��Ȼ���ؼ���nginx���ü���
  
     /usr/local/nginx/sbin/nginx -s reload

  

### �������⣬����������...





