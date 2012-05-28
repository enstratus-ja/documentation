backupDataSource
~~~~~~~~~~~~~~~~

..
    Name
    ++++

名称
++++

..
    backupDataSource - Dumps a data source to the specified file location

backupDataSource - 指定した場所にデータソースをダンプする

..
    Synopsis
    ++++++++

構文
++++

Language: Bash
backupDataSource SERVICE_ID DATA_SOURCE CONFIG_FILE FILE_PATH

..
    Description
    +++++++++++

説明
++++

..
    It invokes the script /mnt/services/$SERVICE_ID/bin/enstratus-backupDataSource , if existent, to backup a Data Source. enstratus-backupDataSource is usually an ad-hoc script meant to backup an specific kind of data source, for example using mysqldump for MySQL databases, pgdump for PostgreSQL, etc.

データソースをバックアップするために、/mnt/services/$SERVICE_ID/bin/enstratus-backupDataSource スクリプトが存在すれば実行します。enstratus-backupDataSource は通常、そのデータソースの種類に応じたスクリプトです。例えば、MySQL データベースに mysqldump を、PostgreSQL に pgdump を使います。

..
    Options
    ++++++++

オプション
++++++++++

SERVICE_ID
    ..
        ID of the service to be backed up. It's provided by enstratus. Service images are stored in /mnt/services/$SERVICE_ID

    バックアップするサービスの ID で、enstratus が提供します。サービスイメージは /mnt/services/$SERVICE_ID に保存されています。

DATA_SOURCE
    ..
        Name of the datasource to be backed up. 

    バックアップするデータソースの名前です。

CONFIG_FILE
    ..
        Configuration file provided by enstratus. It contains information required to perform the backup, such as credentials.

    enStratus が提供する構成ファイルです。認証情報のような、バックアップを実行するのに必要な情報を含みます。

FILE_PATH
    ..
        Temporary file name to be used to store the backup. After a successful backup enstratus will upload the file to the configured cloud storage.

    バックアップの保存に使う一時ファイル名です。バックアップに成功した後で enStratus がこのファイルを設定したクラウドストレージにアップロードします。

..
    Examples
    ++++++++

例
++

backupDataSource a123 testds /mnt/services/a123/cfg/enstratus.cfg /mnt/tmp/123-testds-YYYYMMDD-ID.zip

..
    Invocation
    ++++++++++

起動
++++

..
    This script is called automatically by enstratus if the Data Source has been set for periodic backups, according to the configured frequency.

このスクリプトは、データソースが周期的なバックアップを取るように設定されている場合、設定した頻度により、enStratus が自動的に実行します。

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
