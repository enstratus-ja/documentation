getUnixOS
~~~~~~~~~

..
    Name
    ++++

名称
++++

..
    getUnixOS -  Identifies Linux or Unix flavour

getUnixOS - Linux か Unix かを識別する

..
    Synopsis
    ++++++++

構文
++++

getUnixOS

..
    Description
    +++++++++++

説明
++++

..
    Identifies the Linux or Unix flavour based on the contents of the /usr/bin/lsb_release file

/usr/bin/lsb_release の実行結果に基づいて Linux か Unix かを識別します。

..
    Options
    ++++++++

オプション
++++++++++

..
    None

なし

..
    Examples
    ++++++++

例
++

.. code-block:: sh

	$ getUnixOS 
	UBUNTU

..
    Invocation
    ++++++++++

起動
++++

..
    It may be invoked by any script that needs to determine the Linux flavour in the server

サーバーが Linux かどうかを確認する必要があるときに任意のスクリプトが実行します。

..
    Dependencies
    ++++++++++++

依存関係
++++++++

..
    * No

* なし

..
    Permission
    ++++++++++

権限
++++

..
    No administrative permission required.

管理権限は必要ありません。

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
