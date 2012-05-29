..
    Monitor/Worker
    --------------

モニター/ワーカー
-----------------

..
    Required Knowledge
    ~~~~~~~~~~~~~~~~~~

必要な情報
~~~~~~~~~~

..
    #. IP address/hostname of dispatcher and worker servers

#. ディスパッチャーとワーカーサーバーの IP アドレス/ホスト名

..
    Relevant files 
    ~~~~~~~~~~~~~~

関連ファイル
~~~~~~~~~~~~

..
    monitorWorkerInstaller.tar.gz and the setup directory used during the installation of the
    enStratus Dispatcher software.

monitorWorkerInstaller.tar.gz と、
enStratus ディスパッチャーソフトウェアのインストール中に使った "setup" ディレクトリです。

..
    Extract the monitorWorkerInstaller.tar.gz file. There will be a worker/ directory
    containing the following items:

monitorWorkerInstaller.tar.gz ファイルを解凍してください。
"worker/" ディレクトリに次のように展開されます:

#. files
#. installMonitor.sh 
#. installWorker.sh

..
    Next, move the setup/ directory from the dispatcher directory, so that the contents of the
    monitorWorker/ directory are, after this step:

次に "dispatcher/" ディレクトリから、"monitorWorker/" ディレクトリのコンテンツがある "setup/" ディレクトリへ移動します:

#. files/
#. installMonitor.sh 
#. installWorker.sh
#. setup/

..
    Move the setup directory that was used during the installation of the dispatcher service
    and, as root, execute the installMonitor.sh and then the installWorker.sh script.

ディスパッチャーサービスのインストールに使った "setup" ディレクトリを移動して、
root で、installMonitor.sh を実行してから、installWorker.sh スクリプトを実行します。

..
    Follow the prompts to complete the installation of the services.  

このサービスのインストールを完了するために画面の指示に従ってください。

..
    Upon completion of this step, you will have installed and configured the enStratus monitor
    and worker services.  The setup/install.credentials file will be appended with the list of
    the configuration files used to configure the worker service.

この手順の完了時に、enStratus のモニターとワーカーサービスのインストールと設定が行われます。
setup/install.credentials ファイルは、ワーカーサービスの設定ファイルの一覧が追加されます。

..
    Monitor/Worker Configuration Files
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

モニター/ワーカー構成ファイル
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none

  [ Monitor Configuration Files ]

  /services/monitor/bin/assign
  /services/monitor/bin/controller
  /services/monitor/bin/monitor
  /services/monitor/bin/pinger
  /services/monitor/classes/enstratus-km-client.cfg
  /services/monitor/classes/enstratus-provisioning.cfg
  /services/monitor/classes/mq.cfg
  /services/monitor/etc/cloud.properties
  /services/monitor/etc/monitors.cfg

  [ Workers Configuration Files ]

  /services/worker/classes/dasein-persistence.properties
  /services/worker/classes/enstratus-km-client.cfg
  /services/worker/classes/enstratus-provisioning.cfg
  /services/worker/classes/worker.properties
  /services/worker/classes/mq.cfg
  /services/worker/bin/pinger
  /services/worker/bin/worker
  /services/worker/bin/publisher
  /services/worker/bin/subscriber
