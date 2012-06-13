..
    Overview
    --------

.. _agent_overview:

概要
----

..
    The enStratus agent is composed of a lightweight tomcat application used for communicating
    with the enStratus provisioning server and a set of associated shell scripts. The shell
    scripts are responsible for executing some actions on the server and are extensible by end
    users.

enStratus エージェントは、enStratus のプロビジョニングされたサーバーと通信する軽量の tomcat アプリケーションと、関連するシェルスクリプトのツール群で構成されています。このシェルスクリプトは、サーバー上で複数のアクションの実行し、エンドユーザーが拡張できます。

..
    The agent listens on port 2003 and takes action based on user input as in the case of
    adding a user to a system (the addUser script) and also automates actions such as
    attaching, formatting, encrypting, and mounting volumes as part of a fully automated
    enStratus deployment. Communication to and from the enStratus provisioning server is
    encrypted using SSL.

エージェントは、2003番ポートでリクエストを受け付け、システムにユーザーを追加する (addUser スクリプト) といった、ユーザー入力からアクションを実行します。また、enStratus のデプロイメントを自動化処理の一部として、ボリュームの接続、フォーマット、暗号化、マウントといったアクションを自動化します。enStratus のプロビジョニングされたサーバーとの通信は、SSL を使って暗号化されます。

..
    The enStratus agent is suitable for use on many popular GNU/Linux distributions such as
    Ubuntu, Debian, Cent OS, and Fedora. Additionally, the enStratus agent works on Windows
    Server 2003/2008. The agent functions in both 32- and 64-bit environments.

enStratus エージェントは、Ubuntu, Debian, CentOS, Fedora のような、人気のある GNU/Linux ディストリビューションで使えます。また、enStratus エージェントは、Windows Server 2003/2008 でも動作します。32ビットと64ビットの両方の環境でエージェントは機能します。

..
    The enStratus agent and the associated scripts can be found in /enstratus on a GNU/Linux
    system, and in C:\enstratus on a Windows server.

enStratus エージェントと関連するスクリプトは、GNU/Linux システムでは /enstratus に、Windows サーバーでは C:\enstratus にあります。

..
    Functionality
    ^^^^^^^^^^^^^

機能
^^^^

..
    Installing the enStratus agent opens the server to the full functionality provided by
    enStratus including user management, automation, scheduled termination, statistics,
    logging, and alerting.

enStratus エージェントをインストールすると、
ユーザー管理、自動化、スケジュールされた終了処理、統計、ログ、アラートを含む enStratus が提供する完全な機能を使えます。

..
    enStratus will monitor servers that have the agent installed and alert when status changes
    occur as in the case of an unexpected termination of the server. In an automated
    deployment, enStratus will take the further step of restoring lost servers.

enStratus は、エージェントがインストールされたサーバーを監視して、予期しない終了といった、サーバーの状態が変更したときに警告を発生します。自動デプロイメントにおいては、enStratus は、失ったサーバーのリストア処理に、さらに手順がかかります。
