..
    Key Manager
    -----------

キーマネージャ
--------------

..
    The enStratus Key/Credentials Management service is a tomcat service installed to
    /services/km. 

enStratus 鍵/認証情報管理サービスは、/services/km にインストールされる tomcat サービスです。

..
    Key/Credentials Mangager Overview
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

キー/クレデンシャルマネージャーの概要
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    The enStratus Key/Credentials management system is responsible for the secure handling of cloud credentials
    and any other sensitive information provided via the enStratus console or API. Information is stored in an
    encrypted, de-identified database and is not accessible to users.

enStratus 鍵/認証情報管理システムは、クラウドの認証情報と enStratus コンソールやその API 経由で提供された機密情報をセキュアに扱います。これらの情報は暗号化して特定できないデータベースに保存されて、ユーザーからはアクセスできません。

..
    Starting Key Manager
    ~~~~~~~~~~~~~~~~~~~~

キーマネージャーの開始
~~~~~~~~~~~~~~~~~~~~~~

..
    To start the Key Management service:

鍵管理サービスを開始するには次のようにします:

.. code-block:: bash

	/etc/init.d/enstratus-km start

..
    Key Manager Start Process
    ^^^^^^^^^^^^^^^^^^^^^^^^^

キーマネージャーの開始プロセス
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..
    The init script passes the start argument to /services/km/bin/tomcat, which starts the km service.

init スクリプトは、km サービスを開始する /services/km/bin/tomcat に "start" という引数を渡します。

.. code-block:: bash

	Starting Key Manager.
	Using CATALINA_BASE:   /services/km/tomcat
	Using CATALINA_HOME:   /services/km/tomcat
	Using CATALINA_TMPDIR: /services/km/tomcat/temp
	Using JRE_HOME:       /usr/lib/jvm/java-6-sun

..
    The tomcat service will start, and you should see a java service running on port 2013.

tomcat サービスを開始したら、2013番ポートで実行されている java サービスを確認します。

.. code-block:: bash

	netstat -tnlup | grep 2013
	tcp6       0      0 :::2013                 :::*                    LISTEN 7159/java  

..
    Stopping Key Manager
    ~~~~~~~~~~~~~~~~~~~~

キーマネージャーの停止
~~~~~~~~~~~~~~~~~~~~~~

..
    To stop the Key Management service:

鍵管理サービスを停止するには次のようにします:

.. code-block:: bash

	/etc/init.d/enstratus-km stop

	Stopping Key Manager.
	Using CATALINA_BASE:   /services/km/tomcat
	Using CATALINA_HOME:   /services/km/tomcat
	Using CATALINA_TMPDIR: /services/km/tomcat/temp
	Using JRE_HOME:       /usr/lib/jvm/java-6-sun

..
    Key Manager Stop Process
    ^^^^^^^^^^^^^^^^^^^^^^^^

キーマネージャーの停止プロセス
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..
    The init script passes the stop argument to /services/km/bin/tomcat, which stops the km service.

init スクリプトは、km サービスを停止する /services/km/bin/tomcat に "stop" という引数を渡します。
