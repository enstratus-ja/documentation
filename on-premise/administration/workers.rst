..
    Workers
    -------

.. _workers:

ワーカー
--------

..
    Worker Overview
    ~~~~~~~~~~~~~~~~

ワーカーの概要
~~~~~~~~~~~~~~

..
    The enStratus worker service consists of two components, a publisher and a subscriber. At a very high level,
    these components:

enStratus ワーカーサービスは、2つのコンポーネント、パブリッシャー (publisher) とサブスクライバー (subscriber) で構成されます。これらのコンポーネントの高水準なものです:

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
