..
    Servers
    -------

.. _saas_servers:

サーバー
--------

..
    enStratus monitors all servers in your account. Use the green actions button to access
    your server. If the enStratus agent is not installed on the server, the options available
    are limited to getting information, rebooting, pausing/starting, or terminating the
    server. If the enStratus agent is installed on a running server, additional functionality
    is included in the actions menu.  

enStratus は、アカウント内の全てのサーバーを監視します。アクションボタンを使ってサーバにアクセスします。サーバに enStratus エージェントがインストールされていない場合、利用できるオプションは、サーバ情報の取得、再起動、一時停止/起動、終了に限定されています。enStratus エージェントが実行中のサーバーにインストールされている場合、追加機能がアクションメニューに表示されます。

..
    Expanded information 
    ~~~~~~~~~~~~~~~~~~~~

補足情報
~~~~~~~~

..
    * **Info**: Expanded information regarding server attributes. Including comprehensive hardware information such as logical volumes attached, filesystems used, encryption, and memory.
    * **Analytics**: A graphical representation of CPU Load (in %) over the last hour.
    * **Console**: Hypervisor information.
    * **Agent**: Agent logging capturing events such as adding/removing users, Host Intrusion Detection System alerts, and customizable information messages. 

* **Info**: サーバー属性に関する拡張情報を表示します。接続された論理ボリューム、使用中のファイルシステム、暗号化、メモリなどの包括的なハードウェア情報を含みます。
* **Analytics**: 過去1時間の CPU 負荷のグラフィカルな表示 (%) です。
* **Console**: ハイパーバイザー情報です。
* **Agent**: エージェントロギングは、ユーザーの追加/削除、ホスト侵入検知システムのアラート、カスタマイズ可能な情報メッセージといったイベントをログ出力します。

..
    Make Image
    ~~~~~~~~~~

イメージの作成
~~~~~~~~~~~~~~

..
    Making a machine image means making a saved copy of the server state for future use.
    Machine images will show up in the tab. Machine images should be made whenever changes are
    made to the operating system such as patches or updates. 

マシンイメージの作成は、将来使うサーバーの状態を保存したコピーを作ることです。マシンイメージはタブに表示されます。マシンイメージは、オペレーティングシステムへのパッチやアップデートが行われたときに毎回作るべきです。

..
    Make Snapshot
    ~~~~~~~~~~~~~

スナップショットの作成
~~~~~~~~~~~~~~~~~~~~~~

..
    Making a snapshot means creating a differential backup of any attached volumes. 

スナップショットの作成は、接続されている全てのボリュームの差分バックアップを作ることです。

..
    Shell/Remote Access
    ~~~~~~~~~~~~~~~~~~~

シェル/リモートアクセス
~~~~~~~~~~~~~~~~~~~~~~~

..
    Shell (Linux) and remote (Windows) access refers to creating user accounts on running
    servers. Each user in enStratus is assigned a user code of the form p123. When remote
    access is granted on a Linux server, a home user account is created on that server and the
    public SSH credentials defined in the enStratus user profile are set for the user. On
    Windows, a home account is created and the user can access the running server using the
    RDP password set in the enStratus profile.

シェル (Linux) とリモート (Windows) アクセスは、実行中のサーバーのユーザーアカウントの作成に関連しています。enStratus 内の各ユーザーは、p123 といった形式のユーザーコードが割り当てられています。Linux サーバーに対するリモートアクセスを許可するとき、ホームユーザーアカウントが、そのサーバー上で作成されます。そして、enStratus のユーザープロフィールで定義したパブリックな SSH の認証情報をそのサーバー上のユーザーに設定します。Windows では、ホームアカウントが作成され、ユーザーは enStratus プロフィールに設定した RDP パスワード使って実行中のサーバーにアクセスできます。

.. note::
   ..
       Before granting shell/remote access to a server, the user must define their
       public SSH key and RDP password in their user profile. If the credentials change, the
       remote servers are not notified of the change. To ensure the new credentials are used, the
       user must first be removed and re-added to remote access so the changes can propagate to
       their account. 

   サーバーへのシェル/リモートアクセスを許可する前に、ユーザーはプロフィールの SSH 公開鍵と RDP パスワードを定義する必要があります。この認証情報を変更しても、リモートサーバーにはその変更が通知されません。新しい認証情報を確実に使うには、まずユーザーの認証情報を削除して、アカウントの変更が反映されるようにリモートサーバーに再度追加する必要があります。

..
    Reboot
    ~~~~~~

再起動
~~~~~~

..
    Reboot the running server. Rebooting does not change the IP address of the server. 

実行中のサーバーを再起動します。再起動はサーバの IP アドレスを変更しません。

..
    Pause
    ~~~~~

一時停止
~~~~~~~~

..
    Pause the running server. enStratus still monitors the server. IP address will change upon starting. 

実行中のサーバーを一時停止します。enStratus はその後もサーバーを監視しています。IP アドレスは、起動時に変更されます。

..
    Terminate
    ~~~~~~~~~

終了
~~~~

..
    Terminate the instance. No data on the instance will be saved.

インスタンスを終了します。インスタンス上のデータは保存されません。

..
    To rename a running server, click on the server name indicated by a brown dashed line. A
    text window will appear. Enter the desired name and select OK. The hostname of the server
    will be changed.

実行中のサーバーの名前を変更するには、サーバー名をクリックします。テキスト画面が表示されます。変更したい名前を入力し、"OK" を選択します。サーバのホスト名が変更されます。

..
    To change the label color of a running server, click on the label color and choose the
    desired color from the resulting choices.

実行中のサーバーのラベルの色を変更するには、ラベルの色をクリックして得られた選択肢の中から希望する色を選択します。
