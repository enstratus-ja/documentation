..
    Console
    -------

コンソール
----------

..
    The enStratus console is a tomcat service installed to /services/console.

enStratus コンソールは、/services/console にインストールされる tomcat サービスです。

..
    Console Overview
    ~~~~~~~~~~~~~~~~

コンソールの概要
~~~~~~~~~~~~~~~~

..
    The enStratus console service is a tomcat service that provides the web front-end, or enStratus user console.

enStratus コンソールサービスは、web のフロントエンド、または enStratus のユーザーコンソールを提供する tomcat サービスです。

..
    Starting Console
    ~~~~~~~~~~~~~~~~

コンソールの起動
~~~~~~~~~~~~~~~~

..
    To start the console service:

コンソールサービスを開始するには次のようにします:

.. code-block:: bash

	/etc/init.d/enstratus-console start

..
    Console Start Process
    ^^^^^^^^^^^^^^^^^^^^^

コンソールプロセスの開始
^^^^^^^^^^^^^^^^^^^^^^^^

..
    The console init script performs the following action:

コンソールの init スクリプトは、次のアクションを実行します:

..
    #. Executes /services/console/bin/tomcat, passing it the argument: start. This starts the console process.

#. /services/console/bin/tomcat に "start" 引数を渡して実行します。これは、コンソールプロセスを開始します。

..
    Stopping Console
    ~~~~~~~~~~~~~~~~

コンソールの停止
~~~~~~~~~~~~~~~~

..
    To stop the console service:

コンソールサービスを停止するには次のようにします:

.. code-block:: bash

	/etc/init.d/enstratus-console stop

..
    Console Stop Process
    ^^^^^^^^^^^^^^^^^^^^

コンソールの停止プロセス
^^^^^^^^^^^^^^^^^^^^^^^^

..
    The console init script performs the following action:

コンソールの init スクリプトは、次のアクションを実行します:

..
    #. Executes /services/console/bin/tomcat, passing it the argument: stop. This stops the console process.

#. /services/console/bin/tomcat に "stop" 引数を渡して実行します。これは、コンソールプロセスを停止します。

