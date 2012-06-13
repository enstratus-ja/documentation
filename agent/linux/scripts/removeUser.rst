removeUser
----------

..
    Name
    ~~~~

名称
~~~~

..
    removeUser - Removes shell access for the specified user.

removeUser - 指定したユーザーのシェルアクセスを削除する

..
    Synopsis
    ~~~~~~~~

構文
~~~~

removeUser USER_ID

..
    Description
    ~~~~~~~~~~~

説明
~~~~

..
    It removes a system user account from Linux/Unix servers.

Linux/Unix のサーバーから、システムのユーザーアカウントを削除します。

..
    Options
    ~~~~~~~

オプション
~~~~~~~~~~

USER_ID
    ..
        User name to be removed. User Ids in enStratus follow the pattern pXXX, where XXX is a numeric sequence.

    ユーザー名です。enStratus のユーザー ID である pXXX の XXX の番号をユーザー ID に使います。

..
    Invocation
    ~~~~~~~~~~

起動
~~~~

..
    This script is called when a user is removed manually from a running server using the Shell Access control in the Servers list.

このスクリプトは、サーバーリストのシェルアクセス制御を使って実行中のサーバーから手動でユーザーを削除するときに実行されます。

..
    Dependencies
    ~~~~~~~~~~~~

依存関係
~~~~~~~~

* sudo
* userdel

..
    Permissions
    ~~~~~~~~~~~

権限
~~~~

..
    It is called by the enStratus user. It needs sudo authority for deleting the user.

enstratus ユーザーが実行します。ユーザーを削除するために sudo 権限が必要です。

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
