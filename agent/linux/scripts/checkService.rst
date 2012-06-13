checkService
------------

..
    Name
    ~~~~

名称
~~~~

..
    checkService - This script is used to determine the "health" of a service

checkService - このスクリプトはサービスが健全な状態かを調べるために使われます

..
    Synopsis
    ~~~~~~~~

構文
~~~~

checkService SERVICE_ID

..
    Description
    ~~~~~~~~~~~

説明
~~~~

..
    This script is used to determine the "health" of a service. It is meant to be user-extensible. The way to use this script is to write a script called
    enstratus-check and put it in the /bin directory of your service image.
    The enStratus provisioning server will call this script during the launch of the service. If the script returns a code of "OK", the service will be
    marked as running. If not, it will be marked as impaired.

このスクリプトはサービスが健全な状態かを調べるために使われます。このスクリプトはユーザーが拡張できます。このスクリプトを利用するには、enstratus-check というファイル名のスクリプトを作成して、サービスイメージの /bin ディレクトリにそのスクリプトを置きます。enStratus のプロビジョニングサーバーは、サービスの起動中にこのスクリプトを呼び出します。このスクリプトが "OK" のコードを返す場合、このサービスは実行中と表示されます。そうでない場合は、障害として表示されます。

..
    Options
    ~~~~~~~

オプション
~~~~~~~~~~

SERVICE_ID
    ..
        ID of the service to be checked. It's provided by enstratus. Service images are stored
        in /mnt/services/$SERVICE_ID

    チェックするサービスの ID で、enStratus が提供します。サービスイメージは /mnt/services/$SERVICE_ID に保存されます。

..
    Examples
    ~~~~~~~~

例
~~

checkService a123

..
    Invocation
    ~~~~~~~~~~

起動
~~~~

..
    This script is called automatically by enstratus during the launch of the service.

このスクリプトは、サービスの起動中に enStratus が自動的に実行します。

..
    Dependencies
    ~~~~~~~~~~~~

依存関係
~~~~~~~~

..
    * None

* なし

..
    Permission
    ~~~~~~~~~~

権限
~~~~

..
    It is called by the enstratus user.

enstratus ユーザーが実行します。

..
    Overrides
    ~~~~~~~~~

オーバーライド
~~~~~~~~~~~~~~

..
    Override: No

オーバーライド: 不可

..
    Replace: Yes

置き換え: 可
