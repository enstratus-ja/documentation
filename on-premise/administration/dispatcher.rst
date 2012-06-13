..
    Dispatcher
    ----------

.. _dispatcher:

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
    virtual machines provisioned in the cloud.

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

..
    Dispatcher Logging
    ~~~~~~~~~~~~~~~~~~

ディスパッチャーのログ
~~~~~~~~~~~~~~~~~~~~~~

..
    By default, the dispatcher process logs to: 

デフォルトでは、ディスパッチャー処理は、次のファイルにログ出力されます:

.. code-block:: bash

   /services/dispatcher/tomcat/logs/catalina.out

..
    What's in the dispatcher logs? It depends on the logging level being used by the
    dispatcher process. The logging level is set in:

ディスパッチャーのログとは何でしょうか？ディスパッチャープロセスのログレベルによって変わります。ログレベルは次のファイルに設定されています:

.. code-block:: bash

   /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/log4j.xml

#. INFO

   ..
       With INFO logging set, very little information will be passed to the log file. 

   INFO ログは、ログファイルに少ししかログ出力しません。

#. WARN

#. DEBUG

#. TRACE

..
    Dispatcher Troubleshooting
    ~~~~~~~~~~~~~~~~~~~~~~~~~~

ディスパッチャーのトラブルシューティング
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    The dispatcher is a very stable process and does not require much attention. However,
    here are some areas to consider when managing the dispatcher process.

ディスパッチャーは非常に安定したプロセスであり、あまり注意を払う必要はありません。しかし、ここではディスパッチャーのプロセスを管理するときに考慮する内容を説明します。

..
    1. Restarting the Dispatcher

1. ディスパッチャーの再起動

.. note::
   ..
       Stopping the dispatcher service will cause enStratus to be unusable. 

   ディスパッチャーサービスを停止すると、enStratus は使えなくなります。

..
    Here are some helpful commands to stop and start the dispatcher service, as well as
    tail the logs. Put these commands in your .bashrc as an alias or a function.

ログの末尾を確認する tail コマンドと、ディスパッチャーサービスの停止と開始を行う便利なコマンドがあります。これらのコマンドを .bashrc にエイリアスか、関数として保存します。

  1. alias startDispatcher='/etc/init.d/enstratus-dispatcher start'

  2. alias stopDispatcher='/etc/init.d/enstratus-dispatcher stop'

  3. alias tailDispatcher='tail -f /services/dispatcher/tomcat/logs/catalina.out'

..
    Once these are set, start the dispatcher process like this:

これらの設定を行って、ディスパッチャーを次のように起動します:

.. code-block:: bash

  startDispatcher && tailDispatcher

..
    And you'll be able to start and tail the logs in one line. Very helpful. Why is tailing
    the log useful?

1行でプロセスの開始とログの末尾の確認が行えます。これはかなり役に立ちます。どうしてログの末尾を確認するのでしょうか？

..
    2. Registering for the first time

2. 初回登録

..
    3. Entering Cloud Credentials

3. クラウドの認証情報の入力

   ..
       It can be helpful to watch the dispatcher logs when entering cloud credentials.

   クラウドの認証情報を入力するときにディスパッチャーのログを見ていると便利です。

..
    4. Log sizes 

4. ログサイズ

   ..
       If the installation is new, it is quite likely that the logging levels are set high

   新規インストールの場合は、ログレベルが高く設定されている可能性が高いです。
