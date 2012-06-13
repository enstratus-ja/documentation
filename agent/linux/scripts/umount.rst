umount
------

..
    Name
    ~~~~

名称
~~~~

..
    umount - It umounts any filesystem mounted at a given folder 

umount - 所定のフォルダーにマウントされたファイルシステムをアンマウントする

..
    Synopsis
    ~~~~~~~~

構文
~~~~

umount MOUNT_POINT

..
    Description
    ~~~~~~~~~~~

説明
~~~~

..
    It umount any filesystem mounted at MOUNT_POINT . Aditionally it removes any related entry in /etc/fstab.

MOUNT_POINT の任意のファイルシステムをアンマウントします。さらに /etc/fstab の関連するエントリーを削除します。

..
    Options
    ~~~~~~~

オプション
~~~~~~~~~~

MOUNT_POINT
    ..
        Directory to be unmounted

    アンマウントするディレクトリ

..
    Invocation
    ~~~~~~~~~~

起動
~~~~

..
    This script is called when:

このスクリプトは次のときに実行されます:

..
    * A Volume is dettached from server in the Volume list page.

* "Volume" 一覧ページでサーバーからボリュームが取り外すとき

..
    Dependencies
    ~~~~~~~~~~~~

依存関係
~~~~~~~~

* sudo

..
    Permissions
    ~~~~~~~~~~~

権限
~~~~

..
    It is launched by the enstratus user. It needs sudo authority for umounting a device. 

enstratus ユーザーが実行します。デバイスをアンマウントするために sudo 権限が必要です。

..
    Overrides
    ~~~~~~~~~

オーバーライド
~~~~~~~~~~~~~~

..
    Override: Yes, pre and post

オーバーライド: 可、事前と事後

..
    Replace: Yes

置き換え: 可
