..
    Prerequsites
    ------------

前提条件
--------

..
    Automation is often a task with many moving parts, here are some things to consider before
    attempting automation.

自動化には、多くの流動的な要素をもつ処理がよくあります。ここでは自動化を試みる前に考慮することを説明します。

..
    Cloud
    ~~~~~

クラウド
~~~~~~~~

..
    Your cloud provider must be reliable enough to start VM in a timely fashion. A scalable
    application stack will typically require the starting and stopping of many vm
    simultaneously.

利用中のクラウドプロバイダに、必要なときすぐに VM を起動できるといった信頼性がなければなりません。スケーラブルなアプリケーションスタックは通常、多くの VM の起動と停止を同時に行う必要があります。

..
    Storage
    ~~~~~~~

ストレージ
~~~~~~~~~~

..
    enStratus considers two types of cloud storage: Block and File. File storage is also known
    as object storage. enStratus automation depends heavily on cloud files storage. 

enStratus は、2種類のクラウドストレージを使えます。ブロックとファイルです。ファイルストレージは、オブジェクトストレージとしても知られています。enStratus の自動化機能は、クラウドのファイルストレージにかなり依存しています。

..
    Block storage is sometimes referred to as a "data" disk offering. This type of storage can
    also be quite useful during automation, although it is not required.

ブロックストレージは、"データ" ディスクオファリングと呼ぶこともあります。必須ではありませんが、この種類のストレージは自動化にとても便利です。

..
    Application
    ~~~~~~~~~~~

アプリケーション
~~~~~~~~~~~~~~~~

..
    Attempting to do automation (scaling, recovery, cross-cloud) requires intimate application
    knowledge. The biggest challenge when it comes to automation is at the application layer. 

自動化 (スケーリング、リカバリー、クロスクラウド) を行うには、アプリケーションに対する深い知識が必要です。自動化における最大の課題はアプリケーション層です。

..
    Being able to handle a dynamically provisioned infrastructure on an application is the
    first step to being able to leverage dynamically provisioned resources. 

アプリケーション上で動的にプロビジョニングされたインフラストラクチャを操作できることが、動的にプロビジョニングされたリソースを活用することの第一歩です。

..
    Best Practices
    ~~~~~~~~~~~~~~

ベストプラクティス
~~~~~~~~~~~~~~~~~~

..
    #. IP Addresses. Often, IP addresses change with every newly provisioned instance. A cloudy application will be able to leverage this for scalability.
    #. Storage. Storing data on ephemeral storage is risky, putting application/database data on more persistent data storage is preferable.
    #. Backups. enStratus considers two types of backups: Snapshots and Service. Used in combination, these backups provide a very reliable and customizable solution.

        * Snapshots: Backups accomplished by taking a snapshot of a data volume. The result of this operation is a snapshot.
        * Services: Backups accomplished by calling a user defined script. The result of this operation is a file, which can be stored in cloud files storage.

    #. Disaster Recovery. Disaster recovery for enStratus means storing the files resulting
       from service backups in a geographically distinct cloud region (EC2 East, West, etc...) or
       a separate cloud altogether. 

#. IPアドレス: 多くの場合、IP アドレスは新たにプロビジョニングされたインスタンス毎に変更します。クラウドのアプリケーションは、スケーラビリティのためにこれを活用できるようになります。

#. ストレージ: データを一時的なストレージ上に格納するのは危険です。永続的なデータストレージにアプリケーション/データベースのデータを保存するのが望ましいです。

#. enStratus はスナップショットとサービスという2種類のバックアップを扱います。組み合わせて使うと、これらのバックアップはとても信頼性が高く、カスタマイズ可能なソリューションを提供します。

   * スナップショット: データボリュームのスナップショットを取るバックアップです。この操作はスナップショットを取ります。
   * サービス: ユーザー定義スクリプトを実行することでバックアップを取ります。この操作は、クラウドファイルストレージに格納されたファイルをバックアップします。

#. ディザスタリカバリー: enStratus は、地理的に異なったクラウドリージョン (EC2 East, West 等)、または完全に独立したクラウドにあるサービスのバックアップファイルを保存します。
