addUser
-------

..
    NAME
    ~~~~

名称
~~~~

..
    addUser - Grants the specified user shell access to the server

addUser - 指定したユーザーにサーバーへのシェルアクセスを許可する

..
    SYNOPSIS
    ~~~~~~~~

構文
~~~~

addUser CUST_ID USER_ID FIRST_NAME LAST_NAME ADMINISTRATOR

..
    DESCRIPTION
    ~~~~~~~~~~~

説明
~~~~

..
    It creates a system user for Linux/Unix servers. It can be created as a regular non-privileged user or as an administrative one that can use sudo to gain root privileges . Additionally enStratus copies user's public key to ~/.ssh/authorized_keys to allow secure passwordless authentication.

Linux/Unix サーバーにシステムユーザーを作成します。このユーザーは、普通の非特権ユーザー、または管理上のユーザーとして、sudo を使って root 権限を取得できます。さらに enStratus は、セキュアなパスワード無し認証を許可するために ~/.ssh/authorized_keys にユーザーの公開鍵をコピーします。

..
    OPTIONS
    ~~~~~~~

オプション
~~~~~~~~~~

CUST_ID
    ..
        Customer id within enStratus. It is used as the Linux primary group for the new the user.

    enStratus の顧客 ID です。作成するユーザーの Linux のプライマリーグループとして使われます。

USER_ID
    ..
        User name to be created. User Ids in enStratus follow the pattern pXXX, where XXX is a numeric sequence.

    ユーザー名です。enStratus のユーザー ID である pXXX の XXX の番号をユーザー ID に使います。

FIRST_NAME
    ..
        First name of the user according to his/her profile

    ユーザーの名前 (ファースネーム) です。

LAST_NAME
    ..
        Last name of the user according to his/her profile.

    ユーザーの姓名 (ラストネーム) です。

ADMINISTRATOR
    ..
        If set to "true" the user will have administrative privileges via sudo.

    "true" を設定すると、ユーザーが sudo 経由で管理権限を持てるようになります。

..
    INVOCATION
    ~~~~~~~~~~

起動
~~~~

..
    This script is called when a user is added manually to a running server using the Shell Access control in the Servers list.

このスクリプトは、サーバーリストのシェルアクセス制御を使って実行中のサーバーに手動でユーザーを追加するときに実行されます。

..
    DEPENDENCIES
    ~~~~~~~~~~~~

依存関係
~~~~~~~~

..
    * openssl for automatically generating a strong password.

* sudo
* useradd/usermod
* openssl: 自動的に強力なパスワードを生成する

..
    PERMISSIONS
    ~~~~~~~~~~~

権限
~~~~

..
    It is launched by the enStratus user. It needs sudo authority for creating the user.

enstratus ユーザーが実行します。ユーザーを作成するために sudo 権限が必要です。

..
    OVERRIDES
    ~~~~~~~~~

オーバーライド
~~~~~~~~~~~~~~

..
    Override: Yes, pre and post

オーバーライド: 可、事前と事後

..
    Replace: Yes

置き換え: 可
