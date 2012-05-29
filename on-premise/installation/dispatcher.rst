..
    Dispatcher
    ----------

ディスパッチャー
----------------

..
    Required Knowledge
    ~~~~~~~~~~~~~~~~~~

必要な情報
~~~~~~~~~~

..
    #. IP address/hostname of Key Managment server
    #. Credentials and location information for Rabbit MQ
    #. IP addresses of dispatcher, monitor, and worker servers

#. 鍵管理サーバーの IP アドレス/ホスト名
#. RabbitMQ のロケーション情報と認証情報
#. ディスパッチャー、モニター、ワーカーサーバーの IP アドレス

..
    Relevant files 
    ~~~~~~~~~~~~~~

関連ファイル
~~~~~~~~~~~~

..
    dispatcherInstaller.tar.gz and the setup directory used during the installation of the
    enStratus Key Management software.  Extract the dispatcherInstaller.tar.gz file. There
    will be a dispatcher/ directory containing the following items:

dispatcherInstaller.tar.gz と enStratus の鍵管理ソフトウェアのインストール中に使った "setup" ディレクトリです。dispatcherInstaller.tar.gz ファイルを解凍してください。"dispatcher/" ディレクトリに次のように展開されます:

..
    Next, move the setup/ directory from the km directory, so that the contents of the
    dispatcher/ directory are, after this step:

次に "km" ディレクトリから、"dispather/" ディレクトリのコンテンツがある "setup/" ディレクトリへ移動します:

#. files/
#. installDB.sh
#. installDispatcher.sh
#. setup/

..
    Move the setup directory that was used during the installation of the key management
    service into the dispatcher directory and, as root, execute the installDispatcher.sh
    script. Follow the prompts to complete the installation of the dispatcher service.  Upon
    completion of this step, you will have installed and configured the enStratus dispatcher
    service and the provisioning and analytics databases.  

鍵管理サービスのインストールに使った "setup" ディレクトリに移動して、root で "dispatcher" ディレクトリで入り、installDispatcher.sh スクリプトを実行します。ディスパッチャーサービスのインストールを完了するために画面の指示に従ってください。この手順の完了時に、データベース分析、プロビジョニング、enStratus ディスパッチャーサービスのインストールと設定を完了します。

..
    The setup/install.credentials file will be appended with the username and password used by
    the dispatcher service to connect to its database along with a list of the configuration
    files used to configure the dispatcher service.

setup/install.credentials ファイルには、ディスパッチャーサービスの設定ファイルの一覧と一緒に、そのデーターベースへ接続するためにディスパッチャーサービスが使うユーザー名とパスワードが追加されます。

..
    Dispatcher Configuration Files
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

ディスパッチャー構成ファイル
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none

  [ Dispatcher Configuration Files ]

  /services/dispatcher/bin/tomcat
  /services/dispatcher/bin/enstratus
  /services/dispatcher/bin/pinger
  /services/dispatcher/tomcat/webapps/ROOT/META-INF/context.xml
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/mq.cfg
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-km-client.cfg
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-provisioning.cfg
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/dasein-persistence.properties
  /services/dispatcher/tomcat/conf/server.xml
