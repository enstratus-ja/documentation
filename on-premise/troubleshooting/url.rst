..
    Changing Install URL
    --------------------

インストール URL の変更
-----------------------

..
    To change the root url of your enStratus cloud endpoint, go to the host where the console
    databases are installed.

enStratus クラウドのエンドポイントのルート url を変更するには、コンソールデータベースがインストールされているホストに移動します。

..
    To view the settings for your current endpoint, issue the following commands:

現在のエンドポイントの設定を表示するには、次のコマンドを実行します:

.. code-block:: mysql

  mysql> select application id, main address from application;

  +------------------+-------------------+
  | application_id   | main_address      |
  +------------------+-------------------+
  |                1 | iaas.endpoint.com |
  | 1100000000000001 | cms               |
  +------------------+-------------------+

.. code-block:: mysql

  mysql> select address id, address from web address;

  +------------+-------------------------+
  | address_id | address                 |
  +------------+-------------------------+
  |          4 | cms.cloud.enstratus.com |
  |          1 | iaas.endpoint.com       |
  |          3 | dev.cloud.enstratus.com |
  +------------+-------------------------+

..
    Unless you know what you are doing, leave the cookie domain for your endpoint as NULL.

内容を把握した上で、エンドポイントの cookie ドメインを NULL にします。

..
    As an example, we will update the domain to be cloud.supercorp.com. Issue the following
    commands:

例として、cloud.supercorp.com のドメインを更新します。次のコマンドを実行します:

.. code-block:: mysql

  mysql> update web address set address='cloud.supercorp.com' where address id=1;

  mysql> select application id, main address from application;

  +------------------+---------------------+
  | application_id   | main_address        |
  +------------------+---------------------+
  |                1 | cloud.supercorp.com |
  | 1100000000000001 | cms                 |
  +------------------+---------------------+


.. code-block:: mysql

  mysql> select address id, address, cookie domain from web address;

  +------------+-----------------------------+----------------+
  | address_id | address                     | cookie_domain  |
  +------------+-----------------------------+----------------+
  |          4 | cms.cloud.enstratus.com     | NULL           |
  |          1 | cloud.supercorp.com         | NULL           |
  |          3 | dev.cloud.enstratus.com     | NULL           |
  +------------+-----------------------------+----------------+

..
    Update enstratus-console.cfg
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^

enstratus-console.cfg の更新
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..
    Finally, the last thing to change is a file on the console server:

最後の作業として、コンソールサーバーのファイルを変更します。

/services/console/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-console.cfg

.. code-block:: bash

  refererList=https://iaas.endpoint.com,http://iaas.endpoint.com

..
    **change to:**

**次のように変更します:**

.. code-block:: bash

  refererList=https://cloud.supercorp.com,http://cloud.supercorp.com

..
    Finally, restart the console service.

最後に、コンソールサービスを再起動します。
