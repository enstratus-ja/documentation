backupService
~~~~~~~~~~~~~

..
    Name
    +++++

名称
++++

..
    backupService - Backs up the target service.

backupService - 対象サービスのバックアップを取る

..
    Synopsis
    ++++++++

構文
++++

backupService SERVICE_ID FILE_PATH

..
    Description
    +++++++++++

説明
++++

..
    enStratus invokes the script /mnt/services/$SERVICE_ID/bin/enstratus-backupService, if it
    exists, to backup a service. enstratus-backupService is usually an ad-hoc script meant to backup an specific kind of service.

サービスをバックアップするために、/mnt/services/$SERVICE_ID/bin/enstratus-backupService スクリプトを実行します。enstratus-backupService は通常、そのサービスの種類に応じたスクリプトです。

..
    Options
    +++++++

オプション
++++++++++

SERVICE_ID
    ..
        ID of the service to be backed up. It's provided by enstratus. Service images are stored in /mnt/services/$SERVICE_ID

    バックアップするサービスの ID で、enstratus が提供します。サービスイメージは /mnt/services/$SERVICE_ID に保存されています。

FILE_PATH
    ..
        Temporary file name to be used to store the backup. After a successful backup enstratus will upload the file to the configured cloud storage.

    バックアップの保存に使う一時ファイル名です。バックアップに成功した後で enStratus がこのファイルを設定したクラウドストレージにアップロードします。

..
    Examples
    ++++++++

例
++

backupService a123 /mnt/tmp/123-testservice-YYYYMMDD-ID.zip

..
    Invocation
    ++++++++++

起動
++++

..
    This script is called automatically by enstratus if the Service has been set for periodic backups, according to the configured frequency.

このスクリプトは、サービスが周期的なバックアップを取るように設定されている場合、設定した頻度により、enStratus が自動的に実行します。

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
    Override: Yes, pre and post

オーバーライド: 可、事前と事後

..
    Replace: Yes

置き換え: 可
