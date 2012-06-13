..
    Provided Images
    ---------------

.. _agent_provided_images:

イメージの提供
--------------

..
    The enStratus team provides some machine images that are pre-installed with the enStratus
    agent. These images are configured for use up to and including functioning as a member of
    an automated enStratus deployment. To that end, several changes have been made to the
    images which will be covered here.

enStratus チームは、enStratus エージェントがプリインストールされた複数のマシンイメージを提供しています。これらのイメージは、enStratus の自動デプロイメントのメンバーとしての機能を含み、最大限に利用するように設定されています。そのため、ここで説明するイメージには複数の変更が行われています。

..
    By default, enStratus images come with the OSSEC host-based intrusion detection system.
    OSSEC alerting is integrated into the enStratus alerting system, so you will receive
    alerts based on events triggered by OSSEC both in the enStratus console, and depending on
    your alerts settings, via email. OSSEC is available only on the GNU/Linux platform.

デフォルトでは、enStratus イメージに OSSEC ホストベースの侵入検知システムが付属しています。OSSEC アラートは、enStratus のアラートシステムに統合されています。そのため、OSSEC がトリガーするイベントによるアラートを受け取り、enStratus コンソールやアラート設定による電子メールの両方で受け取れます。OSSEC は、GNU/Linux プラットフォームでのみ利用できます。

..
    enStratus images have installed some software packages to prepare servers started from
    that image for utilization in a wide range of purposes. The list of packages installed on
    enStratus images includes:

enStratus イメージは、このイメージから開始するサーバーが広範囲な目的で利用できるように複数のソフトウェアパッケージをインストールしています。enStratus イメージにインストールされているパッケージ一覧です:

.. hlist::
   :columns: 3
  
   * zip
   * unzip
   * build-essential
   * python-mysqldb
   * xfsprogs
   * libapache2-mod-jk
   * cryptsetup
   * python-json
   * tomcat6
   * postfix
   * mysql-server
   * mdadm
   * sysstat
   * ha-proxy
   * secure-delete
   * apache2
   * cronolog

..
    Not all of these packages are strictly necessary for using enStratus successfully.
    Examples of packages that are not required but are installed are cryptsetup, apache, and
    mysql. If, for example, cryptsetup is not installed, automated encryption of volumes will
    not be possible.

厳密には、これらのパッケージ全てが enStratus を正常に使うのに必要なわけではありません。必須ではありませんが、インストールされているパッケージの例としては、cryptsetup, Apache, mysql などがあります。
例えば、cryptsetup がインストールされていない場合、ボリュームの自動暗号化ができません。

..
    All of the software used by enStratus should be readily available in the distribution
    repositories.

enStratus が使う全てのソフトウェアは、ディストリビューションのリポジトリで簡単に利用できるパッケージにするべきです。

..
    Some init scripts that would normally be in place are also moved to prepare the image for
    use in an automated enStratus deployment. For example, the mysql init script
    /etc/init.d/mysql is removed to prepare the image for use in conjunction with the mysql
    service image where enStratus handles the configuration, installation of the database,
    permissioning, and starting of the mysql service on an attached volume. More information
    on how service images work in a deployment can be found in the documentation on
    automation

通常の場所に置かれている init スクリプトも enStratus の自動デプロイメントで使うイメージを準備するために移動されます。例えば、mysql の init スクリプトの /etc/init.d/mysql は、enStratus が設定、データーベースのインストール、権限設定、mysql サービスを開始してボリュームを接続する MySQL のサービスイメージと、このイメージを組み合わせて使う準備をするために削除されます。デプロイメントにおけるサービスイメージの仕組みの詳細については、自動化機能のドキュメントで解説しています。

..
    All enStratus images also disable SSH access via password authentication. SSH access is
    available only via a public key authentication using the public key located in the user
    profile. SSH access as root user is also disabled. The root password is unknown.

また、全ての enStratus イメージは、パスワード認証経由の SSH アクセスを無効にしています。SSH アクセスは、ユーザープロフィールに置いた公開鍵を使った認証経由でのみ利用できます。root ユーザでの SSH アクセスはできません。root パスワードも分かりません。
