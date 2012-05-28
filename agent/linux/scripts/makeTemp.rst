makeTemp
~~~~~~~~

..
    Name
    ++++

名称
++++

..
    makeTemp -  Shell script to setup the enStratus temp directory

makeTemp - enStratus の一時ディレクトリを設定するシェルスクリプト

..
    Synopsis
    ++++++++

構文
++++

makeTemp

..
    Description
    +++++++++++

説明
++++

..
    It creates /mnt/tmp folder and gives ownership to the enstratus user and group, preventing access to other users

/mnt/tmp フォルダーを作成し、他のユーザーからアクセスできないように enstratus ユーザーとグループに所有権を与えます。

..
    Options
    +++++++

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

	$ makeTemp 
	
..
    Invocation
    ++++++++++

起動
++++

..
    Dependencies
    ++++++++++++

依存関係
++++++++

* sudo

..
    Permission
    ++++++++++

権限
++++

..
    Run by the enstratus user. It needs sudo to create the temp folder and assign the correct ownership and permission.

enstratus ユーザーが実行します。一時フォルダーを作成して、正しい所有者と権限を与えるために sudo 権限が必要です。

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
