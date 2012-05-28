lockFileSystems
~~~~~~~~~~~~~~~

..
    Name
    ++++

名称
++++

..
    lockFileSystems -  Locks all mounted XFS partitions

lockFileSystems - マウントされた全ての XFS パーティションをロックする

..
    Synopsis
    ++++++++

構文
++++

lockFileSystems

..
    Description
    +++++++++++

説明
++++

..
    It prevents access to all mounted XFS partitions using the xfs_freeze tool as a required step for creating volume snapshots.

ボリュームのスナップショットを作成するために必要な手順として、xfs_freeze ツールにより、マウントされた全 XFS パーティションにアクセスできなくなります。

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

	$ lockFileSystems 
	
..
    Invocation
    ++++++++++

起動
++++

..
    It is called by volume snapshot scripts

ボリュームのスナップショットスクリプトが実行します。

..
    Dependencies
    ++++++++++++

依存関係
++++++++

* sudo
* xfs_freeze

..
    Permission
    ++++++++++

権限
++++

..
    Run by the enstratus user. It needs sudo to run the xfs_freeze command

enstratus ユーザーが実行します。xfs_freeze コマンドを実行するために sudo 権限が必要です。

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
