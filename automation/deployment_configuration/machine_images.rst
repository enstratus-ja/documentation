..
    Machine Images/Templates
    ------------------------

マシンイメージとテンプレート
----------------------------

.. note::
   .. 
       Creating "golden" or "master" images is common practice. Best practice is to
       utilize tools that are specially suited the task of configuration management. enStratus
       can leverage the power of both Chef and/or Puppet. enStratus also offers its own
       configuration management engine that is a good introduction to the concept.

   "ゴールデン" または "マスター" イメージを作成するのは一般的なプラクティスです。ベストプラクティスは、構成管理のタスクに特化したツールを使うことです。enStratus は Chef や Puppet のどちらのツールも活用できます。さらに enStratus 自身も入門に適した独自の構成管理エンジンを提供しています。

..
    A machine image is a template from which servers are started. This document assumes a high
    degree of familiarity with the process of image creation and maintenance. Methods for
    maintaining machines with respect to versioning will be addressed. In an automated
    environment, the enStratus agent *must* be installed on a template prior to configuring a
    deployment.

マシンイメージは、サーバーが開始されるテンプレートです。このドキュメントは、イメージの作成とメンテナンス処理についてかなり精通していることを想定しています。バージョン管理に関するマシンをメンテナンスする方法を扱います。自動化された環境では、デプロイメントを構成する前に enStratus エージェントがテンプレート上でインストールされる *必要* があります。

..
    Versioning
    ~~~~~~~~~~

バージョン管理
~~~~~~~~~~~~~~

..
    If you are operating in a deployment, enStratus can help you manage the version of machine
    image you are using in your launch configurations. This concept is addressed as part of
    the auto-rollout feature of enStratus.

デプロイメントで操作をしているなら、enStratus は起動構成に使っているマシンイメージのバージョンを管理するのに役立ちます。この概念は、enStratus の自動展開機能の一部に対応します。

..
    In short, you should patch servers running in your deployment as you see fit, and ensure
    you maintain an equally patched version of the AMI defined in your launch configuration so
    that when/if a scale or recovery event occurs, you utilize the correct machine image
    version for the newly created servers.

要するに、デプロイメントにおいて実行中のサーバーに適切なパッチを当てます。このパッチを当てたイメージは、起動構成で定義された AMI にパッチを当てたバージョンとして保持することを保証します。そのため、スケールまたはリカバリーイベントが発生した場合、新たに作成したサーバーの適切なマシンイメージバージョンとして使えます。

..
    Dependencies
    ~~~~~~~~~~~~

依存関係
~~~~~~~~

..
    enStratus has very few true dependencies. It depends on Java, so ensure you have the
    latest JDK installed to support the Agent. Additionally, when you are operating in an
    automated deployment environment, we recommend installing the following software:

enStratus の実際の依存関係はかなり少ないです。Java に依存するので、エージェントに対応した最新の JDK がインストールされていることを確認してください。さらに自動化されたデプロイメント環境で操作するときは、以下のソフトウェアのインストールをお奨めします:

.. tabularcolumns:: |l|l|l|
   ..
       +-------------------+----------------------------------+--------------+
       | Package           | Purpose                          | Note         |
       +===================+==================================+==============+
       | zip               | Backups                          | Recommended  |
       +-------------------+----------------------------------+--------------+
       | openssl           | Adding Users                     | **Required** |
       +-------------------+----------------------------------+--------------+
       | unzip             | Service install, backups         | Recommended  |
       +-------------------+----------------------------------+--------------+
       | build-essential   | OSSEC installation and more      | Optional     |
       +-------------------+----------------------------------+--------------+
       | xfsprogs          | XFS filesystem functionality     | Optional     |
       +-------------------+----------------------------------+--------------+
       | libapache2-mod-jk | mod_jk load balancing            | Optional     |
       +-------------------+----------------------------------+--------------+
       | postfix           | Sending mail notifications       | Optional     |
       +-------------------+----------------------------------+--------------+
       | cryptsetup        | Encryption (LUKS)                | Recommended  |
       +-------------------+----------------------------------+--------------+
       | haproxy           | Load Balancing                   | Optional     |
       +-------------------+----------------------------------+--------------+
       | cronolog          | Logging                          | Optional     |
       +-------------------+----------------------------------+--------------+
       | sysstat           | OS metrics                       | **Required** |
       +-------------------+----------------------------------+--------------+
       | secure-delete     | Securely delete files            | Recommended  |
       +-------------------+----------------------------------+--------------+
       | mysql-server      | Running MySQL Databases          | Optional     |
       +-------------------+----------------------------------+--------------+

+-------------------+----------------------------------+--------------+
| パッケージ        | 目的                             | 備考         |
+===================+==================================+==============+
| zip               | バックアップ                     | 推奨         |
+-------------------+----------------------------------+--------------+
| openssl           | ユーザー追加                     | **必須**     |
+-------------------+----------------------------------+--------------+
| unzip             | インストールとバックアップ       | 推奨         |
+-------------------+----------------------------------+--------------+
| build-essential   | OSSEC インストールなど           | 任意         |
+-------------------+----------------------------------+--------------+
| xfsprogs          | XFS ファイルシステムの拡張機能   | 任意         |
+-------------------+----------------------------------+--------------+
| libapache2-mod-jk | mod_jk 負荷分散                  | 任意         |
+-------------------+----------------------------------+--------------+
| postfix           | メール通知の送信                 | 任意         |
+-------------------+----------------------------------+--------------+
| cryptsetup        | 暗号化 (LUKS)                    | 推奨         |
+-------------------+----------------------------------+--------------+
| haproxy           | 負荷分散                         | 任意         |
+-------------------+----------------------------------+--------------+
| cronolog          | ロギング                         | 任意         |
+-------------------+----------------------------------+--------------+
| sysstat           | OS の状態監視                    | **必須**     |
+-------------------+----------------------------------+--------------+
| secure-delete     | セキュアなファイル削除           | 推奨         |
+-------------------+----------------------------------+--------------+
| mysql-server      | MySQL データベース               | 任意         |
+-------------------+----------------------------------+--------------+
