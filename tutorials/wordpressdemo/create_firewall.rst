..
    Create Firewall
    ~~~~~~~~~~~~~~~

ファイアウォールの作成
~~~~~~~~~~~~~~~~~~~~~~

..
    Let's create a firewall (security group) for use in this tutorial.

このチュートリアルで使うファイアウォール (セキュリティグループ) を作成しましょう。

..
   Create Firewall

.. figure:: ./images/firewall0.png
   :height: 400px
   :width: 800 px
   :scale: 50 %
   :alt: Create Firewall
   :align: center

   Firewall の作成

..
    Open ports 22 and 80 to your IP for testing. enStratus will automatically adjust the
    firewall for the applications deployed according to the services > ports settings.

テスト目的でサーバーの IP アドレス宛の22番と80番ポートを開けてください。enStratus は、"services > ports settings" からデプロイするアプリケーションのファイアウォールを自動的に設定します。
