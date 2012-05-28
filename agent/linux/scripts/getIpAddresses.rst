getIpAddresses
~~~~~~~~~~~~~~

..
    Name
    ++++

名称
++++

..
    getIpAddresses - retrieve the internal (private) IP of the server using the ifconfig command

getIpAddresses - ifconfig コマンドを使ってサーバーの内部 (プライベート) IP アドレスを取得する

..
    Synopsis
    ++++++++

構文
++++

getIpAddresses

..
    Description
    +++++++++++

説明
++++

..
    It retrieves the internal (private) IP of the server using the ifconfig command

ifconfig コマンドを使ってサーバーの内部 (プライベート) IP アドレスを取得する

..
    Options
    +++++++

オプション
++++++++++

..
    None

なし

..
    Invocation
    ++++++++++

起動
++++

..
    It can be used by service configuration scripts when it is not possible to obtain the private IP address using other methods.

他の方法を使ってプライベート IP アドレスを取得できないときにサービス構成スクリプトが実行します。

..
    Dependencies
    ++++++++++++

依存関係
++++++++

* ifconfig

..
    Permissions
    +++++++++++

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
