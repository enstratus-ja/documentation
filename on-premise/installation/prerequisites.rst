..
    Prerequisites
    -------------

.. _prerequisites:

前提条件
--------

..
    Before you begin
    ~~~~~~~~~~~~~~~~

始める前に
~~~~~~~~~~

.. note::
   ..
       When installing MySQL, please set a root password, it will be required during the installation of services that depend on MySQL.

   MySQL をインストールするときに root パスワードを設定してください。MySQL に依存するサービスをインストールするときに必要です。

..
    During the installation enStratus will auto-generate mysql users and passwords for the database services it installs. enStratus generates good passwords.

enStratus のインストール中に、インストールするデータベースサービスの mysql ユーザーとパスワードを自動生成します。enStratus は、適切なパスワードを生成します。

  ..
      Example: K0B6KheBDtrANJOEp1LuWpCmjF

  例: K0B6KheBDtrANJOEp1LuWpCmjF

..
    If generating your own passwords is something you would like to do. Please do so after
    completing the installation by referencing the appropriate configuration files and at your
    own risk.  The details of installing this software is dependent on your distribution.
    Please have this software installed before attempting an installation of the enStratus
    cloud management software.

自分で独自のパスワードを生成したいなら、それも行えます。インストールが完了した後に、各自のリスクで適切な設定ファイルを参照することで、パスワード生成を行ってください。このソフトウェアのインストールの詳細は、利用中のディストリビューションに依存します。enStratus クラウド管理ソフトウェアのインストールを試す前に、このソフトウェアを調べておいてください。

..
    Key Generation
    ~~~~~~~~~~~~~~

鍵の生成
~~~~~~~~

..
    The purpose of this step is to generate encryption keys and create some bootstrap MySQL
    information for the Dispatcher and Console services.

この手順の目的は、暗号化鍵を生成して、ディスパッチャーとコンソールサービスのために MySQL のブートストラップ情報を作成することです。

..
    Required Knowledge
    ~~~~~~~~~~~~~~~~~~

必要な知識
~~~~~~~~~~

..
    #. enStratus License Key
    #. Desired url for the console service. For example, cloud.mycorporation.com 
    #. IP address of the server that will run the console server.

#. enStratus ライセンスキー
#. 必要なコンソールサービスの url。例えば cloud.mycorporation.com
#. コンソールサーバーを実行するサーバーの IP アドレス

..
    Move the keygen bundle to the server that will contain the Key Management service and extract it.
    Once extracted, there will be a keygen/ directory containing the following items:

keygen の関連ファイル群を、鍵管理とその解凍を行うサーバーへ持っていきます。解凍すると、"keygen/" ディレクトリに次のように展開されます。

#. classes
#. enstratus-utilities.jar 
#. files
#. keygen.sh
#. setup

..
    Enter the keygen/ directory and, as root, execute the keygen.sh script. You will be
    promted for the three pieces of information listed above. The outcome of this script will
    be the creation of a file called install.credentials located in the setup/ directory.

"keygen/" ディレクトリに root で移動して、keygen.sh スクリプトを実行します。冒頭で説明した3つの情報が表示されます。このスクリプトを実行すると、install.credentials というファイルを "setup/" ディレクトリに作成します。

..
    For the database-driven services of Key Manager, Dispatcher, and Console, the respective
    credentials section of this file are critical. If the installer crashes or is interrupted
    after the database installs have run and the credentials have been appended and you want
    to start over with the installation of that service, you must first delete the section in
    the install.credentials file and the databases that were created.  The requirement to do
    this will cease as the installer is improved.

キーマネージャー、ディスパッチャー、コンソールのデータベース駆動サービスには、このセクションで説明している認証情報ファイルが不可欠です。インストーラーがクラッシュしたり、データベースのインストールを実行した後に中断してしまった場合、この認証情報が追加されてしまっています。サービスのインストールをやり直したいなら、install.credentials ファイルのセクションと作成されたデータベースを最初に削除する必要があります。これを行うために、改良したインストーラーは停止するようになります。

..
    Other Information
    ~~~~~~~~~~~~~~~~~

その他の情報
~~~~~~~~~~~~

..
    Required operating system is Linux. Architecture x86_64. Preferred distribution is
    Ubuntu/Debian. While nothing technologically prevents a windows installation, I'll leave
    that as an exercise for the reader. :)

必要なオペレーティングシステムは Linux、アーキテクチャは x86_64 です。推奨ディストリビューションは Ubuntu/Debian です。技術的に Windows のインストールを阻むものはありませんが、みなさんの課題用として置いておきます。 :)

..
    The server onto which enStratus is installed can be virtual. They should not, however, be
    part of the pool of VMs enStratus is destined to manage.

enStratus をインストールしたサーバーは仮想化できます。とは言え、そういったサーバーは、enStratus が管理する仮想マシンプールの対象にはなりません。

..
    All machines must have direct, non-vpn network access to each other.

全てのマシンが直接、互いに対して非 VPN ネットワークにアクセスできる必要があります。

..
    Provisioned/managed VMs must have direct, non-proxied, non-vpn access to the dispatcher
    and worker servers.

プロビジョニング/管理された仮想マシンは、ディスパッチャーやワーカーサービスと非プロキシ、非 VPN ネットワークにアクセスできる必要があります。

..
    If an enStratus engineer is performing the installation, we will require shell access with
    root privileges to all of the machines onto which enStratus is to be installed.  

enStratus のエンジニアがインストールを行う場合は、enStratus がインストールされた全マシンに root 権限でのシェルアクセスが必要です。

..
    enStratus engineers can provide their public SSH key to you for remote access or they can
    work through a VPN.  We require port 22, 80, and 443 access externally to our office IP
    address: 216.250.165.28.

enStratus のエンジニアは、リモートアクセス用に SSH の公開鍵を提供したり、VPN 経由で作業を行えます。私たちのオフィスの IP アドレス: 216.250.165.28 から 22, 80, 443 のポート番号にアクセスできる必要があります。

..
    Requesting installations over a "screenshared" session such as webex is *strongly*
    discouraged. It is highly inefficient and greatly increases the possibility of error.

webex のような、"screenshared (スクリーンを共有する)" セッションでのインストールは *なるべく* 推奨しません。その理由は、効率が極端に悪く、エラーが起こる可能性が大幅に増加します。

..
    The enStratus software installation process is most suited to a systems administrator with
    knowledge of how to install the prerequisites and do basic configuration.

enStratus ソフトウェアのインストール作業は、前提条件のインストールや基本的な設定の知識をもったシステム管理者を対象としています。

..
    The file (object) storage server will be used for object (file) storage as is essential to
    do things like automation and downloading of service images and scripts to running virtual
    machines.

オブジェクト (ファイル) ストレージのように使うファイル (オブジェクト) ストレージサーバーは、実行中の仮想マシンの自動化、スクリプトやサービスイメージのダウンロードといったことを行うのに不可欠なものです。

..
    enStratus engineers will also assist on-premise clients with the installation and
    configuration of the enStratus agent, a pre-requisite for doing automation.

enStratus のエンジニアは、オンプレミスクライアントのインストール、enStratus エージェントの設定、自動化に必要となる前提作業も支援します。
