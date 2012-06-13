..
    Installation
    ------------

.. _agent_installation:

インストール
------------

.. hint::
   ..
       The easiest way to determine what version of the enStratus agent is installed on
       an instance is to use the actions menu associated with the instance. Choose actions > info
       and select the tab labeled "Guest".

   インスタンスにインストールされた enStratus エージェントのバージョンを確認する最も簡単な方法は、インスタンスに関連付けられたアクションメニューを使うことです。"actions > info" を選択して "Guest" タブを確認してください。

Debian/Ubuntu
^^^^^^^^^^^^^

.. code-block:: bash

  $ apt-get install gcc sun-java6-jdk sysstat sudo secure-delete 
  $ sudo dpkg -i enstratus-latest.deb

Chef
^^^^

..
    Using Chef to install and configure a VM for using the enStratus agent is the most
    efficient and *idempotent* way of installing the enStratus agent.

enStratus エージェントを使う VM の設定とインストールを行うために Chef を使うことは、enStratus エージェントをインストールする最も効率的、且つ冪等 (idempotent) な方法です。

Windows
^^^^^^^

