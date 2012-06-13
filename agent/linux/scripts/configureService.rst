configureService
----------------

..
    Name
    ~~~~

名称
~~~~

..
    configureService - Launcher for service-specific configuration script

configureService - サービス固有の構成スクリプトのランチャー

..
    Synopsis
    ~~~~~~~~

構文
~~~~

configureService USER_ID CUSTOMER_ID SERVICE_ID [[ SSL_ADDRESS CERT_FILE_PATH KEY_FILE_PATH ] CHAIN_FILE_PATH ]

..
    Description
    ~~~~~~~~~~~

説明
~~~~

..
    enStratus invokes the script /mnt/services/$SERVICE_ID/bin/enstratus-configure, if it exists, to run a service specific configuration script

サービス固有の構成スクリプトを実行するために、/mnt/services/$SERVICE_ID/bin/enstratus-configure が存在すれば enStratus が実行します。

..
    Options
    ~~~~~~~

オプション
~~~~~~~~~~

USER_ID
    ..
        User under whose authority the service configuration process will run. It can be set in the configuration of the service, otherwise enStratus will assign one.

    サービスの構成処理を実行する権限をもつユーザーです。サービスの構成で設定できます。設定しない場合は enStratus が割り当てます。

CUSTOMER_ID
    ..
        Customer id within enStratus. 

    enStratus の顧客 ID です。

SERVICE_ID
    ..
        ID of the service to be configured. It's provided by enStratus. Service images are stored in /mnt/services/$SERVICE_ID

    構成するサービス ID で、enStratus が提供します。サービスイメージは /mnt/services/$SERVICE_ID に保存されています。

SSL_ADDRESS
    ..
        When using a SSL certificate, the fully qualified name associated to the certificate

    SSL 認証を利用する場合、証明書に関連付けられた完全修飾名です。

CERT_FILE_PATH
    ..
        When using a SSL certificate, the path to a temporary file containing the certificate file.

    SSL 認証を利用する場合、証明書ファイルを含む一時ファイルへのパスです。

KEY_FILE_PATH
    ..
        When using a SSL certificate, the path to a temporary file containing its private key

    SSL 認証を利用する場合、その秘密鍵を含む一時ファイルへのパスです。

CHAIN_FILE_PATH
    ..
        Path of a file containing additional CA certificated that may be required to validate the certificate.

    証明書の検証を必要とする場合の追加の CA (認証局) 情報を含むファイルのパスです。

..
    Examples
    ~~~~~~~~

例
~~

configureService c100 c100 a12000

..
    Invocation
    ~~~~~~~~~~

起動
~~~~

..
    This script is called automatically by enStratus if the service needs to be configured in that server.

このスクリプトは、サービスがそのサーバーを設定するのに必要とする場合、enStratus が自動的に実行します。

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
    It is called by the enStratus user.

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
    Replace: No

置き換え: 不可
