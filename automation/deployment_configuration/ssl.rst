SSL
---

..
    SSL certificates may be uploaded to enStratus where they will be protected via the same
    encryption methods as any credentials for the customer account. SSL certificates should
    not be imaged onto servers, rather, they should be installed in an automated on-demand
    fashion at the time of server start.

顧客アカウントの認証情報のように同じ暗号化方式を使って保護される enStratus 上で SSL 証明書をアップロードできます。SSL 証明書はイメージファイルのようにサーバーに置くものではなく、サーバーの起動時に自動化されてオンデマンドにインストールされるべきです。

..
    Creating
    ~~~~~~~~

作成
~~~~

..
    Create SSL certificates by any method you desire. enStratus will inform the administrator
    via an alert when the SSL cerfiticate is set to expire via a message of the form:

任意の方法で SSL 証明書を作成します。SSL 証明書にフォームを使って有効期限を設定している場合、enStratus は管理者へその警告を通知します:

.. literalinclude:: ./files/sslExpire

..
    Uploading
    ~~~~~~~~~

アップロード
~~~~~~~~~~~~

..
    To upload your certificate to enStratus, navigate to Infrastructure > SSL Certificates as
    shown:

enStratus に SSL 証明書をアップロードするには、次の図のように "Infrastructure > SSL Certificates" へ移動します:

..
   SSL, Upload

.. figure:: ./images/sslCertificate.png
   :height: 500px
   :width: 800 px
   :scale: 50 %
   :alt: SSL, Upload
   :align: center

   SSL、アップロード

..
    Updating
    ~~~~~~~~

更新
~~~~

..
    To update your SSL certificate, choose an existing certificate from the list and update
    the necessary fields, then save.

SSL 証明書を更新するには、リストから既存の証明書を選択し、必要なフィールドを更新した後で保存します。

..
    Using
    ~~~~~

使用
~~~~

..
    Data sources are used when configuring a service. More is said about this in the section
    on Tiers, which hold services.

サービスを設定するときにデータソースが使われます。詳細については、階層のセクションのサービスを保持するところを参照してください。
