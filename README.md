
## itop FAQ ���������б�

## �ٷ�Wiki������Ҫ��ǽ��

https://wiki.openitop.org/
��������ϸ���ĵ�����

���磬����api���ж��ο���

    https://wiki.openitop.org/doku.php?id=2_3_0:advancedtopics:rest_json&s[]=api

���Զ���itop

    https://wiki.openitop.org/doku.php?id=2_3_0:customization:start

����...

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
 
    SELECT Person JOIN lnkPersonToTeam AS T ON T.person_id = Person.id WHERE T.team_id = :this->manager_group_id

���� 
    

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



### �������⣬����������...





