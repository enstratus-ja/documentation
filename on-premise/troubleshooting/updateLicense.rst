..
    Update License Key
    ------------------

ライセンスキーの更新
--------------------

..
    Updating your enStratus license key can be accomplished using the following steps.

enStratus ライセンスキーの更新は、次の手順で行います。

..
    Required Information
    ~~~~~~~~~~~~~~~~~~~~

必要な情報
~~~~~~~~~~

..
    #. Access to the provisioning database.
    #. License key

#. プロビジョニングされたデータベースへのアクセス
#. ライセンスキー

..
    Updating the Key
    ~~~~~~~~~~~~~~~~

キーの更新
~~~~~~~~~~

.. code-block:: mysql

  update backend_configuration set license_key='abcd1234';

..
    Finishing Up
    ~~~~~~~~~~~~

仕上げ
~~~~~~

..
    Once the key is updated, you will need to restart the dependent services.

キーが更新されると、依存するサービスを再起動する必要があります。

..
    * Dispatcher
    * Workers/Monitors

* ディスパッチャー
* ワーカー/モニター
