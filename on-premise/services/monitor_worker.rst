..
    Monitor
    -------

モニター
--------

..
    The enStratus monitor service is a java service installed to /services/monitor.

enStratus モニターサービスは、/services/monitor にインストールされる java サービスです。

..
    Monitor Overview
    ~~~~~~~~~~~~~~~~

モニターの概要
~~~~~~~~~~~~~~

.. note::
   ..
       The enStratus monitors service is in the process of being deprecated in favor of a more efficient workers process.

   enStratus モニターサービスは、より効率的なワーカープロセスにより、廃止されるプロセスです。

..
    The enStratus monitors service is responsible for maintaining an accurate representation of cloud state,
    checking on the completion of jobs initiated by the dispatcher service, orchestrating server launches and
    service installations.

enStratus モニターサービスは、クラウドの正確な状態情報、ディスパッチャーサービスが開始したジョブの完了チェック、サーバー起動のオーケストレーションやサービスのインストールなどをメンテナンスする役割を担います。

..
    Starting Monitor
    ~~~~~~~~~~~~~~~~

モニターの開始
~~~~~~~~~~~~~~

..
    To start the monitor services:

モニターサービスを開始するには次のようにします:

.. code-block:: bash

	/etc/init.d/enstratus-monitor start

..
    Monitor Start Process
    ^^^^^^^^^^^^^^^^^^^^^

モニターの開始プロセス
^^^^^^^^^^^^^^^^^^^^^^

..
    The monitor init script performs the following actions:

モニターの init スクリプトは、次のアクションを実行します:

..
    #. Executes /services/monitor/bin/assign. This starts the assignment service, which is responsible for controlling the monitor services.
    #. The monitor start process cycles through a list of monitors designated in the file
       called /services/monitor/etc/monitors.cfg, executing a call to /services/monitor/bin/poll,
       with the start argument, as shown. Each monitor process has an associated log file located
       in /services/monitor/log.

#. /services/monitor/bin/assign を実行します。これは、モニターサービスを制御する割り当てサービスを開始します。
#. モニターの開始プロセスは、/services/monitor/etc/monitors.cfg というファイルで指定されたモニターのリストを読み込み、次のように /services/monitor/bin/poll に "start" 引数を渡して実行する処理を繰り返します。各モニターのプロセスは /services/monitor/log にログファイルを保存します。

.. code-block:: bash

	Starting assign
	Starting assignment...
	Started 0.
	Starting monitors.
	/services/monitor/bin/poll start Address 1
	/services/monitor/bin/poll start AutoScaling 1
	/services/monitor/bin/poll start Backup 1
	/services/monitor/bin/poll start Budget 1
	/services/monitor/bin/poll start Dc 1
	/services/monitor/bin/poll start Deployment 1
	/services/monitor/bin/poll start DeploymentAnalytics 1
	/services/monitor/bin/poll start Distribution 1
	/services/monitor/bin/poll start Dns 1
	/services/monitor/bin/poll start ExchangeRate 1
	/services/monitor/bin/poll start ForwardingRule 1
	/services/monitor/bin/poll start Image 1
	/services/monitor/bin/poll start Invoice 1
	/services/monitor/bin/poll start KeyValue 1
	/services/monitor/bin/poll start LoadBalancer 1
	/services/monitor/bin/poll start Maintenance 1
	/services/monitor/bin/poll start Notifications 1
	/services/monitor/bin/poll start Prepayment 1
	/services/monitor/bin/poll start Rdbms 1
	/services/monitor/bin/poll start ScalingEvent 1
	/services/monitor/bin/poll start ScalingEventProcess 1
	/services/monitor/bin/poll start Server 1
	/services/monitor/bin/poll start ServerAnalytics 1
	/services/monitor/bin/poll start Snapshot 1
	/services/monitor/bin/poll start Ssl 1
	/services/monitor/bin/poll start Subscription 1
	/services/monitor/bin/poll start TierAnalytics 1
	/services/monitor/bin/poll start Volume 1
	/services/monitor/bin/poll start VPNGateway 1

..
    Stopping Monitor
    ~~~~~~~~~~~~~~~~

モニターの停止
~~~~~~~~~~~~~~

..
    To stop the monitor services:

モニターサービスを停止するには次のようにします:

.. code-block:: bash

	/etc/init.d/enstratus-monitor stop

..
    Monitor Stop Process
    ^^^^^^^^^^^^^^^^^^^^

モニターの停止プロセス
^^^^^^^^^^^^^^^^^^^^^^

..
    The monitor init script performs the following actions:

モニターの init スクリプトは、次のアクションを実行します:

..
    #. Executes /services/monitor/bin/assign, passing the stop argument. This stops the assignment service.
    #. The monitor start process cycles through a list of monitors designated in the file
       called /services/monitor/etc/monitors.cfg, executing a call to /services/monitor/bin/poll,
       with the stop argument, as shown. Each monitor process has an associated log file located
       in /services/monitor/log.

#. /services/monitor/bin/assign を実行します。これは、モニターサービスを制御する割り当てサービスを停止します。
#. モニターの停止プロセスは、/services/monitor/etc/monitors.cfg というファイルで指定されたモニターのリストを読み込み、次のように /services/monitor/bin/poll に "stop" 引数を渡して実行する処理を繰り返します。各モニターのプロセスは /services/monitor/log にログファイルを保存します。

.. note::
   ..
       The monitor stop process is slow and not terribly reliable. A less elegant, yet faster method for
       terminating the monitor processes is to issue the command:

   モニターの停止プロセスは、遅い上にそれほど信頼性もありません。見た目は悪いですが、モニタープロセスを停止する手っとり早い方法としては、次のコマンドがあります:

   ps -ef | grep onit | awk '{print $2}' | while read line; do kill -9 $line; done

..
    Worker
    ------

ワーカー
--------

.. note::
   ..
       The enStratus worker service is a java service installed to /services/worker. The enStratus monitor services
       are in the process of being migrated to the worker model.

   enStratus ワーカーサービスは /services/worker にインストールされる java サービスです。enStratus モニターサービスは、ワーカーモデルへ移行中です。

..
    Worker Overview
    ~~~~~~~~~~~~~~~~

ワーカーの概要
~~~~~~~~~~~~~~

..
    The enStratus worker service consists of two components, a publisher and a subscriber. At a very high level,
    these components:

enStratus ワーカーサービスは、2つのコンポーネント、パブリッシャー (publisher) とサブスクライバー (subscriber) で構成されます。これらのコンポーネントの高水準なものです:

..
    1. Publisher

1. パブリッシャー

   ..  - The publisher is responsible for pushing actions onto a queue.

   - パブリッシャーは、アクションをキューに追加する役割を担います。

..
    2. Subscriber

2. サブスクライバー

   ..  - The subscriber is responsible for taking actions off of the queue and acting accordingly.

   - サブスクライバーは、必要なときにキューから取り出すアクションを行う役割を担います。

..
    Starting Worker
    ~~~~~~~~~~~~~~~

ワーカーの開始
~~~~~~~~~~~~~~

..
    To start the worker service:

ワーカーサービスを開始するには次のようにします:

.. code-block:: bash

	/etc/init.d/enstratus-workers start

..
    Worker Start Process
    ^^^^^^^^^^^^^^^^^^^^^

ワーカーの開始プロセス
^^^^^^^^^^^^^^^^^^^^^^

..
    The worker init script performs the following actions:

ワーカーの init スクリプトは、次のアクションを実行します:

..
    #. Executes /services/worker/bin/publisher, passing it the argument: start. This starts the publisher process.
    #. Executes /services/worker/bin/subscriber, passing it the argument: start. This starts the subscriber process.

#. /services/worker/bin/publisher に "start" 引数を渡して実行します。これは、パブリッシャープロセスを開始します。
#. /services/worker/bin/subscriber に "start" 引数を渡して実行します。これは、サブスクライバープロセスを開始します。

..
    Stopping Worker
    ~~~~~~~~~~~~~~~

ワーカーの停止
~~~~~~~~~~~~~~

..
    To stop the worker service:

ワーカーサービスを停止するには次のようにします:

.. code-block:: bash

	/etc/init.d/enstratus-workers stop



