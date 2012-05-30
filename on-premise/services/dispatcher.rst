..
    Dispatcher
    ----------

ディスパッチャー
----------------

..
    The enStratus Dispatcher service is a tomcat service installed to /services/dispatcher.

enStratus ディスパッチャーサービスは、/services/dispatcher にインストールされる tomcat サービスです。

..
    Dispatcher Overview
    ~~~~~~~~~~~~~~~~~~~

ディスパッチャーの概要
~~~~~~~~~~~~~~~~~~~~~~

..
    The dispatcher service is the heart of the enStratus provisioning operations. It is responsible for executing
    user-initiated actions from the enStratus console.

ディスパッチャーサービスは、enStratus プロビジョニングオペレーションの中核です。enStratus コンソールからユーザーが開始したアクションを実行する役割を担います。

..
    Starting Dispatcher
    ~~~~~~~~~~~~~~~~~~~

ディスパッチャーの開始
~~~~~~~~~~~~~~~~~~~~~~

..
    To start the Dispatcher service:

ディスパッチャーサービスを開始するには次のようにします:

.. code-block:: bash

	/etc/init.d/enstratus-dispatcher start

..
    Dispatcher Start Process
    ^^^^^^^^^^^^^^^^^^^^^^^^

ディスパッチャーの開始プロセス
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..
    The dispatcher init script performs two actions:

ディスパッチャーの init スクリプトは次の2つを実行します:

..
    #. Executes /services/dispatcher/bin/pinger. This starts the pinger service.
    #. Passes the start argument to /services/dispatcher/bin/tomcat, which starts the dispatcher service. 

#. /services/dispatcher/bin/pinger を実行します。これは pinger サービスを開始します。
#. ディスパッチャーサービスを開始する /services/dispatcher/bin/tomcat に "start" という引数を渡します。

.. code-block:: bash

	Starting pinger.
	Starting Dispatcher.
	Using CATALINA_BASE:   /services/dispatcher/tomcat
	Using CATALINA_HOME:   /services/dispatcher/tomcat
	Using CATALINA_TMPDIR: /services/dispatcher/tomcat/temp
	Using JRE_HOME:       /usr/lib/jvm/java-6-sun

..
    The pinger is an auxiliary service which is responsible for performing a type of heartbeat operation for
    virtual machines provisionined in the cloud.

pinger は、クラウドでプロビジョニングされた仮想マシンの心拍を調べるような役割を担う補助サービスです。

..
    The dispatcher service will start, and a java service will run on port 3302.

ディスパッチャーサービスを開始したら、3302番ポートで実行されている java サービスを確認します。

.. code-block:: bash

	netstat -tnlup | grep 3302
	tcp6       0      0 :::3302                 :::*                    LISTEN 7199/java  

..
    Stopping Dispatcher
    ~~~~~~~~~~~~~~~~~~~

ディスパッチャーの停止
~~~~~~~~~~~~~~~~~~~~~~

..
    To stop the Dispatcher service:

ディスパッチャーサービスを停止するには次のようにします:

.. code-block:: bash

	/etc/init.d/enstratus-dispatcher stop

	root@ubuntu:/home/greg# stopDispatcher 
	Stopping Dispatcher.
	Using CATALINA_BASE:   /services/dispatcher/tomcat
	Using CATALINA_HOME:   /services/dispatcher/tomcat
	Using CATALINA_TMPDIR: /services/dispatcher/tomcat/temp
	Using JRE_HOME:       /usr/lib/jvm/java-6-sun

..
    Dispatcher Stop Process
    ^^^^^^^^^^^^^^^^^^^^^^^

ディスパッチャーの停止プロセス
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..
    The dispatcher init script passes the stop argument to /services/dispatcher/bin/tomcat, which stops the dispatcher
    service.

ディスパッチャーの init スクリプトは、ディスパッチャーサービスを停止する /services/dispatcher/bin/tomcat に "stop" という引数を渡します。

.. note::
   ..
       The stop argument does not stop the pinger service. This is expected behavior.

   "stop" 引数は pinger サービスを停止しません。この動作は仕様です。
