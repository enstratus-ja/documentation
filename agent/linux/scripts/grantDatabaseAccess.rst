grantDatabaseAccess
~~~~~~~~~~~~~~~~~~~

..
    Name
    ++++

名称
++++

..
    grantDatabaseAccess - Triggers a service-specific script for granting database access to a client.

grantDatabaseAccess - データベースへのアクセス権をクライアントに与えるためにサービス固有のスクリプトをトリガーする。

..
    Synopsis
    ++++++++

構文
++++

grantDatabaseAccess SERVICE_ID CONFIG_FILE 

..
    Description
    +++++++++++

説明
++++

..
    It invokes the script /mnt/services/$SERVICE_ID/bin/enstratus-dbgrant , if existent, to allow access to a database from another server

他のサーバーからデータベースへのアクセスを許可する /mnt/services/$SERVICE_ID/bin/enstratus-dbgrant スクリプトが存在すれば実行します。

..
    Options
    +++++++

オプション
++++++++++

SERVICE_ID
    ..
        ID of the service. It's provided by enstratus. Service images are stored in /mnt/services/$SERVICE_ID

    enstratus が提供するサービス ID です。サービスイメージは /mnt/services/$SERVICE_ID に保存されています。

CONFIG_FILE
    ..
        Configuration file provided by enstratus. It contains information required to grant access to a data source, like the remote server IP, database name and credentials .

    enStratus が提供する構成ファイルです。リモートサーバーの IP アドレス、データーベース名や認証情報といったデータソースへのアクセスを許可するために必要な情報が含まれます。

..
    Examples
    ++++++++

例
++

grantDatabaseAccess a123 /enstratus/ws/tomcat/temp/database6625343243682788319.cfg

..
    Invocation
    ++++++++++

起動
++++

..
    This script is called automatically by enstratus during a deployment for any new server in a service depending of a Data Source

このスクリプトは、データソースに依存する任意のサービスが新規にデプロイされるときに enStratus が自動的に実行します。

..
    Dependencies
    ++++++++++++

依存関係
++++++++

..
    * None

* なし

..
    Permission
    ++++++++++

権限
++++

..
    It is launched by the enstratus user.

enstratus ユーザーが実行します。

..
    Overrides
    +++++++++

オーバーライド
++++++++++++++

..
    Override: No

オーバーライド: 不可

..
    Replace: No

置き換え: 不可
