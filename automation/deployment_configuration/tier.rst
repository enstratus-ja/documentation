..
    Tier
    ----

階層
----

..
    A tier is a logically and physically scalable division that contain servers running. Tiers
    may span one or more clouds, so it is possible to have a tier that starts by provisioning
    servers in your private data center but "bursts" when demand dictates additional
    infrastructure into a public cloud provider.

階層は、実行中のサーバーを含む論理的かつ物理的にスケーラブルな部分です。階層は、1つまたは複数のクラウドにまたがる可能性があるので、プライベートデータセンターにサーバーをプロビジョニングすることで開始する階層を設け、追加のインフラストラクチャが必要になったときにパブリッククラウドプロバイダーに "爆発的" に拡大できます。

..
    A launch configuration is logically contained within a tier. In fact, a tier cannot exist
    in any region without a corresponding launch configuration.

起動構成は、階層内にある論理的なものです。実際に、階層は任意のリージョンに対応する起動構成なしでは存在しません。

..
   Tier

.. figure:: ./images/tierHighlighted.png
   :height: 400px
   :width: 400 px
   :scale: 50 %
   :alt: Tier
   :align: center

   階層

..
    Manage Tier, General Information
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

階層の管理、全般的な情報
~~~~~~~~~~~~~~~~~~~~~~~~

..
   Tier, General Information

.. figure:: ./images/tierGeneralInformation.png
   :height: 500px
   :width: 1200 px
   :scale: 50 %
   :alt: Tier, General
   :align: center

   階層と全般的な情報

..
    Managing a tier includes the capability to delete the tier or grant shell access for the
    tier. If the tier is deleted, any associated launch configurations will also be deleted.
    If the shell access option is selected, a dialog box will be presented to the
    administrator for adding shell access to servers running in the tier.

階層の管理には、その層を削除する機能とその層に対するシェルアクセスを与える機能が含まれています。この層が削除された場合、関連付けられた全ての起動構成も削除されます。シェルアクセスのオプションを選択すると、管理者に対して、この層で実行中のサーバーへのシェルアクセスを追加するためのダイアログボックスが表示されます。

..
    Manage Tier, Shell Access
    ~~~~~~~~~~~~~~~~~~~~~~~~~

階層の管理、シェルアクセス
~~~~~~~~~~~~~~~~~~~~~~~~~~

..
   Tier, Shell Access

.. figure:: ./images/tierShellAccess.png
   :height: 300px
   :width: 1000 px
   :scale: 50 %
   :alt: Tier, Shell Access
   :align: center

   階層とシェルアクセス

..
    When servers are started as part of ongoing tier operations, Users designated for shell
    access will be granted shell access shortly after the server has registered with the
    enStratus provisioning server.

サーバーが継続中の層の操作の一部として開始されている場合、シェルアクセスのために設定されたユーザーは、そのサーバーが enStratus のプロビジョニングサーバーに登録された直後にシェルアクセスを許可されます。

..
    The same requirements for shell access in individual servers apply, namely that the
    firewall must be open on the port where SSH is running, and the user must have a public
    key as part of their profile.

個々のサーバーに適用するシェルアクセスの要件として、ファイアウォールの SSH を実行しているポート番号を開けておく必要があります。また、ユーザーはプロフィールの1つとして公開鍵を持たなければなりません。

..
    Tier Scaling Rules, Scaling Rules
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

階層のスケーリングルール、スケーリングルール
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
   Tier, Scaling Rules

.. figure:: ./images/tierScalingRules.png
   :height: 700px
   :width: 1300 px
   :scale: 50 %
   :alt: Tier, Scaling Rules
   :align: center

   階層とスケーリングルール

..
    Scaling rules are where the parameters that govern the scaling of tier resources.

スケーリングルールには、階層のリソースのスケーリングを管理するパラメータがあります。

#. **Minimum Servers**

   ..
       The minimum servers specification sets the minimum required number of servers that must be
       kept running in the tier at all times. If the total number of running servers in the tier
       falls below this threshold, an auto-recovery event will be triggered.

   最小サーバー設定は、常時、その層で実行され続けなければならないサーバーの最小必要数です。もしその層で実行中のサーバーの合計数がこのしきい値を下回ると、自動リカバリーイベントがトリガーされます。

#. **Maximum Servers**

   ..
       The maximum servers specification sets the maximum allowable number of servers for a tier.
       If the demand on the tier is such that additional server resources are required, enStratus
       will scale up to, but not exceed, this value.

   最大サーバ数設定は、その層が許容できるサーバーの最大数を設定します。もしその層で追加サーバーのリソース要求があれば、enStratus はスケールアウトしますが、この最大値を超えることはありません。

#. **Scaling Rules**

..
    There are three options for scaling rules:

スケーリングルールには3つのオプションがあります。

   1. **enStratus** 

      ..
          enStratus scaling options are the ones shown by default. Scaling behavior is
          governed by certain "hardware" parameters described here.

      enStratus のスケーリングオプションはデフォルトで表示されます。スケーリングの動作は、ここで説明する特定の "ハードウェア" パラメーターにより管理されます。

      ..
          enStratus can govern scaling events by monitoring the CPU load of the servers. The CPU
          load is equal to: 15-minute load average/# of CPU. For example, if the system has 2 CPU
          and the load average is 0.89, the CPU threshold reading is 0.445*100 = 44.5.

      enStratus は、サーバーの CPU 負荷を監視することにより、スケーリングイベントを管理できます。CPU 負荷とは [15分間の平均負荷 / CPU の数] です。例えば、システムに2つの CPU があり、平均負荷が 0.89 なら、CPU のしきい値の読み取りは 0.445*100 = 44.5 です。

      .. * Lower CPU Threshold

      * CPU しきい値の下限

        ..
            The lower bound on CPU threshold. If the threshold drops
            below this level and there are more than the minimum number of servers running, 
            servers will be terminated due to the decreased demand.
  
        CPU のしきい値がこのレベルより下回り、且つ実行中のサーバー数が最小サーバー数よりも多いなら、需要の減少によりサーバーを終了します。

      .. * Upper CPU Threshold

      * CPU しきい値の上限
  
        ..
            The upper bound on CPU threshold. If the threshold rises above this level and there are
            less than the maximum number of servers running, servers will be started to meet increased
            demand.

        CPU のしきい値がこのレベルを上回り、且つ実行中のサーバー数が最大サーバー数よりも少ないなら、需要の増加のためにサーバーが起動します。

      .. * Lower RAM Threshold

      * RAM しきい値の下限
  
        ..
            The lower RAM threshold sets the lower bound on RAM usage on a percentage used basis. If
            the threshold drops below this level and there are more than the minimum number of
            required servers running, servers will be scaled down due to decreased demand.

        これは RAM の使用量の下限をパーセントで設定します。RAM のしきい値がこのレベルより下回り、且つ実行中のサーバー数が最小サーバー数よりも多いなら、需要の減少によりサーバーがスケールダウンします。

      .. * Upper RAM Threshold

      * RAM しきい値の上限

        ..
            The upper RAM threshold set the upper bound on RAM usage on a percentage used basis. If
            the threshold is above this threshold and there is room available to scale, servers will
            be scaled up due to increased demand.

        これは RAM の使用量の上限をパーセントで設定します。RAM のしきい値がこのレベルを上回り、且つスケールする余裕があるなら、需要の増加によりサーバーがスケールアウトします。

   2. **Cloud**

      ..
          enStratus can also trigger scaling events based on the properties of the cloud provider.
          If your cloud provider has mechanisms in place to govern scaling, enStratus will defer to
          them if the cloud option is selected.

      enStratus は、クラウドプロバイダーの特性によりスケーリングイベントもトリガーできます。クラウドプロバイダーがスケーリングを管理する所定の仕組みを持っていて、このクラウドオプションが選択された場合、enStratus はそのイベントを延期します。
   
   3. **Custom**

      ..
          Custom scaling rules are by far the most powerful method for controlling scaling events.
          There are inherent problems with reading CPU load by default as CPU isn't really all
          that meaningful of a concept when working in a multi-tenant cloud environment where actual
          CPU are load shared.

      カスタムスケーリングルールは、スケールイベントを制御するためにとても強力な方法です。デフォルトの CPU 負荷を読み込むことは、本質的に問題があります。それはマルチクラウド環境で実行しているときは、実際の CPU 負荷が共有され、CPU が重要な指標ではなくなるからです。

      ..
          In short, custom scaling with enStratus means that on an interval of about 30s, enStratus
          will read the output of a script called /enstratus/bin/scaleCheck. The scaleCheck script
          that controls scaling behavior signals enStratus to scale up, do nothing, or scale down by
          returning 1, 0, or -1, respectively.

      端的に言うと、enStratus のカスタムスケーリングとは、約30秒間毎に enStratus が /enstratus/bin/scaleCheck というスクリプトの出力を読み込むようになります。スケーリングの動作を制御する scaleCheck スクリプトは、enStratus にシグナルを送ります。そのシグナルは、スケールアウト、何もしない、スケールダウンのそれぞれに対応する 1, 0, -1 を返します。

      ..
          A voting mechanism is used by enStratus to determine whether or not to scale the number of
          servers in a group. Essentially, if the majority of servers in a server group
          "vote" to scale up by returning 1, a new server will be started. If the majority
          of servers in a server group vote to scale down by returning -1, a random server in that
          group will be terminated. If most servers vote 0, no scaling will occur.

      enStratus は、グループ内のサーバ数をスケーリングさせるかどうかを判断するために投票機構を使います。グループ内のサーバーの大多数が1を返すことでスケールアウトするように "投票" するなら、新規のサーバーが起動します。グループ内のサーバの大多数が-1を返すことでスケールダウンするように投票する場合は、そのグループ内でランダムに選択されたサーバーを終了させます。また、ほとんどのサーバーが0に投票するなら、スケーリングは行われません。

      ..
          Here is an example of a scaleCheck script that was written to provide a mechanism for
          applying a normalization factor to "small" servers running in EC2.

      ここに EC2 で実行中の "small" サーバーに正規化係数を適用する仕組みを提供する scaleCheck スクリプトの例があります。

.. note::
   ..
       In all cases, enStratus manages the actions of initiating the scale. Each
       scaling event is a server launch, and all of the orchestration/automation around that
       launch is controlled using the parameters set in enStratus 

   全てのケースにおいて、enStratus はスケールを開始するアクションを管理します。各スケーリングイベントは、サーバーの起動であり、その起動に関する調整や自動化は、enStratus で設定した一連のパラメータを使って管理されます。

.. literalinclude:: ./files/scaleCheck
   :language: bash

..
    Scaling Sensitivity
    ~~~~~~~~~~~~~~~~~~~

スケーリング感度
~~~~~~~~~~~~~~~~

#. **違反期間**

   .. #. **Breach Period**

   ..
       The amount of time for which the load average must exceed the upper CPU threshold before a
       scaling event will occur resulting in more servers.

   スケーリングイベントが発生させてサーバーを増やす前に、CPU の負荷平均が上限のしきい値を超えている期間です。

#. **クールダウン期間**

   .. #. **Cooldown Period**

   ..
       The amount of time for which the load average must be below the lower CPU threshold before
       a scaling event will occur resulting in less servers.
       The breach and cooldown periods control the "sensitivity" of the scaling behavior.

   スケーリングイベントが発生させてサーバーを減らす前に、CPU の負荷平均が下限のしきい値を下回っている期間です。違反期間とクールダウン期間は、スケーリング動作の "感度" を制御します。

#. **違反インクリメント**

   .. #. **Breach Increment**

   ..
       The breach increment controls the size of the "step" enStratus uses to scale up or
       down. If the minimum and maximum number of servers specification is such that there is
       room to scale, enStratus will do so by the number of servers specified in the breach
       increment.

   違反インクリメントは、enStratus がスケールアウトまたはダウンするのに使う "step" のサイズを制御します。サーバーの最小数と最大数の設定は、enStratus がスケールさせるサーバー数の許容範囲であり、enStratus は違反インクリメントで指定したサーバー数により、その制御を行います。

   ..
       For example if the minimum and maximum values are 2 and 10, respectively, and the breach
       increment is 2, if demand requires extra resources, the first scaling action will result
       in 4 servers. The same principle applies to scaling down as it does when scaling up.

   例えば、最小値と最大値がそれぞれ2と10で、違反インクリメントが2であるなら、追加リソースを必要とする需要があれば、最初のスケーリングアクションが発生して4サーバーとなります。スケールダウンするときにもスケールアウトのときと同様の原理が適用されます。

.. note::
   ..
       If enStratus scaling rules are in place, enStratus reads the values presented to it
       via a file called /mnt/tmp/stats.properties, that is a product of the
       /enstratus/bin/calculateAgentData script.

   enStratus のスケーリングルールが所定の位置にあるなら、enStratus は /mnt/tmp/stats.properties というファイル経由でその内容を読み込みます。これは /enstratus/bin/calculateAgentData スクリプトが生成します。

..
    Manage Servers, Servers
    ~~~~~~~~~~~~~~~~~~~~~~~

サーバー管理、サーバー
~~~~~~~~~~~~~~~~~~~~~~

..
    Selecting this tab will show the servers running as part of the selected tier. The view
    will aggregate the server list across all regions in the tier.

このタブを選択すると、選択した層の一部として実行中のサーバーが表示されます。このビューは、選択した層の全てのリージョンにまたがるサーバーリストを集約します。

..
   Tier, Servers

.. figure:: ./images/tierServers.png
   :height: 400px
   :width: 1400 px
   :scale: 50 %
   :alt: Tier, Servers
   :align: center

   階層、サーバー

..
    Manage Services, Services
    ~~~~~~~~~~~~~~~~~~~~~~~~~

サーバー管理、サービス
~~~~~~~~~~~~~~~~~~~~~~

..
    From here it is possible to interact with services. To add a service to a tier, first
    select the tier from the diagram. Next navigate to the Manage Service tab shown above.
    Choose Add Service.

ここからは、サービスと対話的にやり取りできます。ある階層にサービスを追加するには、この図から最初にその層を選択します。次に上述した "Manage Service" タブに移動して "Add Service" を選択します。

..
   Tier, Add Service

.. figure:: ./images/addServiceToTier.png
   :height: 500px
   :width: 600 px
   :scale: 50 %
   :alt: Tier, Add Service
   :align: center

   階層、サーバーの追加

..
    A list of available services will be presented. Adding a service requires fairly minimal
    information. The more interesting part of services is in the configuration.

利用可能なサービスのリストが表示されます。サービスの追加には最小限の情報が必要です。この設定はサービスの興味深い部分です。

..
    Selecting this option will present the services that are connected to this tier.

このオプションを選択すると、この層に接続されているサービスを表示します。

..
   Tier, Services

.. figure:: ./images/tierManageService.png
   :height: 400px
   :width: 1400 px
   :scale: 50 %
   :alt: Tier, Services
   :align: center

   階層、サービス

..
    Using the same process, a service was also added to the Database tier. To view all
    services, select the deployment and choose Manage Services. This will cause the console to
    display all of the services installed in all tiers on the deployment.

同じ作業を行って、あるサービスをデータベース層に追加しました。全てのサービスを表示するには、デプロイメントから "Manage Services" タブを選択します。すると、デプロイメント上の全ての層にインストールされた全てのサービスがコンソールに表示されます。

..
   Tier, All Services

.. figure:: ./images/allServices.png
   :height: 400px
   :width: 1400 px
   :scale: 50 %
   :alt: Tier, All Services
   :align: center

   階層、全てのサービス

..
    Configuring Services
    ~~~~~~~~~~~~~~~~~~~~

サービスの設定
~~~~~~~~~~~~~~

..
    Configuring services controls options such as the port upon which the services listen for
    incoming traffic, credentials, and dependencies. To view the configuration options
    associated with a service, click on the green action button for the service:

サービスの設定は、そのサービスが入ってくるトラフィック、認証情報、依存関係を受け付けるためのポート番号などのオプションを制御します。サービスに関連付けられた設定オプションを表示するには、サービスの緑色のアクションボタンをクリックしてください。

..
   Service, Actions

.. figure:: ./images/serviceActions.png
   :height: 600px
   :width: 800 px
   :scale: 50 %
   :alt: Service, Actions
   :align: center

   サービス、アクション

..
    Launch
    ~~~~~~

起動
~~~~

..
   Launch is an option that is reserved for starting services on an already running
   deployment. On the service, enStratus will call the script called
   /mnt/services/$serviceID/bin/enstratus-start.

起動は、すでに実行中のデプロイメント上でサービスを開始するために予約されているオプションです。そのサービスで、enStratus は /mnt/services/$serviceID/bin/enstratus-start というスクリプトを実行します。

.. note::
   ..
       If the deployment is not running, this action is meaningless.

   デプロイメントが実行されていない場合、このアクションは無効です。

..
    Edit
    ~~~~

編集
~~~~

..
   Service, Edit

.. figure:: ./images/editService.png
   :height: 600px
   :width: 800 px
   :scale: 50 %
   :alt: Service, Edit
   :align: center

   サービス、編集

..
    Editing a service presents several options. The options presented here control how
    enStratus treats your service and what information is passed to your service when changes
    occur.

サービスの編集には、複数のオプションが表示されます。ここで提示されるオプションは、enStratusがサービスをどのように扱い、変更が発生したときにどの情報をサービスに渡すかを制御します。

1. **Backup Frequency**

   ..
       The backup frequency setting controls the frequency with which enStratus calls any custom
       backup script located in /mnt/services/$serviceID/enstratus/bin/enstratus-backupService.
       This is a service level backup and enStratus will store the resulting backup file in
       cloud storage.

   バックアップの頻度設定は、enStratus が /mnt/services/$serviceID/enstratus/bin/enstratus-backupService にある任意のカスタムバックアップスクリプトを実行する頻度を制御します。これはサービスレベルのバックアップであり、enStratus はクラウドストレージにそのバックアップファイルを保存します。

2. **Configuration**

   ..
       Configuration is a free form text field that allows an administrator to pass in sensitive
       information to the service. This information makes its way directly into the
       enstratus.cfg file that is passed as an argument to the
       /mnt/services/$serviceID/bin/enstratus-configure as necessary during scaling and starting
       events. Remember that the enstratus.cfg file is securely erased after it is used.

   構成は、管理者がサービスへ渡す機密情報で、自由形式のテキストフィールドです。この情報はスケーリング中とイベントの開始時、必要に応じて /mnt/services/$serviceID/bin/enstratus-configure への引数として渡され、直接 enstratus.cfg ファイルに書き込まれるかもしれません。使用後に enstratus.cfg ファイルは、安全に消去されることに注意してください。

3. **Run as User**

   ..
       The run as user controls the user enStratus will use to start the service.

   これは enStratus をサービスを開始するのに使うユーザーを制御します。

4. **Service Image**

   ..
       The service image is the service image that will be used for the specified service.
       Service images must first be uploaded via Automation > Service Images.

   サービスイメージは、指定されたサービスのために使われるイメージファイルです。サービスイメージは、あらかじめ "Automation > Service Images" からアップロードしておく必要があります。

5. **Scaling Model**

   ..
       The scaling model has four options:

   スケーリングモデルには4つのオプションがあります:

      1. **None** 

         ..
             This option means that no special action will be taken during scaling beyond the
             normal scaling mechanism.

         このオプションは、通常のスケーリングによりスケールしているときに特別なアクションを行いません。

      2. **Load Balanced** 

         ..
             This option tells enStratus to notify a load balancer when a scaling
             event occurs that affects this service.

         このオプションは、このサービスに影響のあるスケーリングイベントを発生させるときにロードバランサーへ通知するよう enStratus に指示します。

      3. **Replicated Database** 

         ..
             This option tells enStratus to treat the first server started in a tier as a master
             and all subsequent servers as slaves. Please refer to the MySQL service image for
             more information about this process.

         このオプションは、ある層で最初に開始したサーバーをマスター、後続の全サーバーをスレーブとして扱うよう enStratus に指示します。この処理の詳細については MySQL サービスイメージのセクションを参照してください。

      4. **Clustered Database** 

         ..
             This option tells enStratus to treat all database servers as peers with no
             master/slave relationship.

         このオプションは、全てのデータベースサーバをマスター/スレーブ関係の無いピアとして扱うよう enStratus に指示します。

6. **SSL Certificate**

   ..
       SSL Certificates may be uploaded to enStratus via the interface at Infrastructure > SSL.

   SSL 証明書は、"Infrastructure > SSL" でのインターフェースから enStratus にアップロードします。

..
   SSL, Add

.. figure:: ./images/sslCertificate.png
   :height: 600px
   :width: 800 px
   :scale: 50 %
   :alt: SSL, Add
   :align: center

   SSL、追加

..
    If a certificate has been uploaded to enStratus, it will be present as an option and
    securely passed in to the servers at launch via the /enstratus/bin/configureService script
    and ultimately to the user-defined /mnt/services/$serviceID/bin/enstratus-configure script
    for use in configuring the service.

証明書が enStratus にアップロード済みの場合は、オプションとして表示されて、起動時に /enstratus/bin/configureService スクリプトにより安全にサーバへ渡されます。最終的には、サービスの設定に使うユーザー定義の /mnt/services/$serviceID/bin/enstratus-configure スクリプトへ渡されます。

..
    In this option, the SSL certificates are passed to the application servers.

このオプションでは、SSL 証明書はアプリケーションサーバーへ渡されます。

7. **Load Balancer SSL**

   ..
       Checking this option will allow the administrator to specify the load balancer as a target
       for the SSL certificate. This option is only available for virtual machine based load
       balancers.

   このオプションを有効にすると、管理者は SSL 証明書の対象としてロードバランサーを指定できます。このオプションは、仮想マシンベースのロードバランサーでのみ使用可能です。

   ..
       SSL certificates may be available to cloud based load balancers, and must be configured
       via your cloud provider as not all cloud support this option.

   SSL 証明書はクラウドベースのロードバランサーにも利用できるかもしれませんが、全てのクラウドがこのオプションに対応しているわけではないので、クラウドプロバイダーを通して設定する必要があります。

8. **Billing Code**

   ..
       It is possible to track tier costs against a billing code. Different tiers within the same
       deployment may have different billing codes.

   課金コードに対する階層のコストを監視できます。同じデプロイメント内の異なる階層は、異なる課金コードを持てます。

9. **Owning Group**

   ..
       The owning group will specify the group attribute for the service.

   所有グループは、サービスのグループ属性を指定します。

..
    Ports
    ~~~~~

ポート番号
~~~~~~~~~~

..
   Service, Ports

.. figure:: ./images/servicePorts.png
   :height: 400px
   :width: 800 px
   :scale: 50 %
   :alt: Service, Ports
   :align: center

   サービス、ポート番号

..
    Adding a service port to a service will configure enStratus to pass in the relevant port
    information to the service via the enstratus.cfg file. If there is a load balancer
    connected to the deployment, it will appear in the Load Balancers selection window. If a
    load balancer is selected, enStratus will ensure that servers that have this service
    installed upon them are connected to the load balancer upon start.

サービスにそのポート番号を追加すると、enstratus.cfg ファイル経由で、そのサービスの該当するポート番号に情報を渡すよう enStratus を設定します。デプロイメントに接続されているロードバランサーがある場合、ロードバランサーの選択画面に表示されます。ロードバランサーが選択されると、enStratus はこういった設定がイントールされたサービスを提供するサーバーが、このロードバランサーに接続できることを保証します。

..
    More specifically, if you have virtual machine-based load balancer specified, and an
    application server has a service installed that is connected to the load balancer,
    enStratus will call /enstratus/bin/startProxy on the load balancer after the service is
    configured on the application server.

より具体的には、仮想マシンベースのロードバランサーが指定されたら、その設定をインストールしたサービスをもつアプリケーションサーバーは、そのロードバランサーに接続されます。enStratus は、このサービスがアプリケーションサーバーで設定された後にロードバランサーの /enstratus/bin/startProxy を実行します。

..
    If a cloud based load balancer such as an elastic load balancer (ELB), enStratus will call
    the correct API command to connect that server to the ELB. The cloud based load balancer
    must be configured beforehand to pass traffic on the correct ports and protocols.

elastic load balancer (ELB) のようなクラウドベースのロードバランサの場合、enStratus はそのサーバーを ELB に接続する適切な API コマンドを呼び出します。クラウドベースのロードバランサーは、あらかじめ適切なポート番号とプロトコルのトラフィックを渡すように設定されている必要があります。

..
    The relevant section of the enstratus.cfg file for ports is shown here: 

enstratus.cfg ファイルのポート番号に関連するセクションは次の通りです:

.. code-block:: bash

  [enstratus]
  port.80.protocol=TCP 
  port.80.publicPort=80 
  port.80.privatePort=80 

..
    Credentials
    ~~~~~~~~~~~

認証情報
~~~~~~~~

..
    Credentials are also securely passed to the service via the enstratus.cfg file during
    deployment start. What happens to these credentials is determined by the actions taken by
    the enstratus-configure script which should be written by the application/service
    architect.

また、認証情報もデプロイメントの開始時に enstratus.cfg ファイル経由で安全にサービスへ渡されます。これらの認証情報をどうするかは、enstratus-configure スクリプトによるアクションで決まります。このスクリプトはアプリケーション/サービスのアーキテクトにより記述されます。

..
   Service, Credentials

.. figure:: ./images/serviceCredentials.png
   :height: 600px
   :width: 700 px
   :scale: 50 %
   :alt: Service, Credentials
   :align: center

   サービス、認証情報

..
    The relevant section of the enstratus.cfg file for credentials is here: 

enstratus.cfg ファイルの認証情報に関連するセクションは次の通りです:

.. code-block:: bash

  [enstratus]
  serviceKeys=admin 
  serviceKey.admin.user=adminUser
  serviceKey.admin.password=trustno1

..
    Data Sources
    ~~~~~~~~~~~~

データソース
~~~~~~~~~~~~

..
   Service, Data Soruce

.. figure:: ./images/serviceDataSources.png
   :height: 400px
   :width: 800 px
   :scale: 50 %
   :alt: Service, Data Soruce
   :align: center

   サービス、データソース

..
   Data Source, Edit

.. figure:: ./images/serviceEditDataSource.png
   :height: 600px
   :width: 800 px
   :scale: 50 %
   :alt: Data Source, Edit
   :align: center

   データソース、編集

..
    A data source is tied only to database services. Data sources are database backup files
    such as a datasource.sql file that have been uploaded to enStratus for use in deployments
    via Automation > Data Sources.

データソースは、データベースサービスにのみ置かれます。データソースは、datasource.sql のようなデータベースのバックアップファイルです。それは "Automation > Data Sources" からデプロイメントで使うために enStratus にアップロードされたものです。

..
    The figure above displays the data source configuration for a MySQL service. The available
    configuration options for data sources and their functions are described here:

上の図は、MySQL サービスのデータソースの設定を表示しています。データソースとその機能に関する利用可能な設定オプションを説明します。

#. **Name**

   ..
       The name is a logical name for the data source as it will appear in the enStratus console.

   名前は、enStratus コンソールに表示されるデータソースの論理名です。

#. **Name in Database**

   ..
       This configuration option ultimately becomes the name of the database itself as in the
       case of a MySQL service.

   この設定オプションは、MySQL サービスの場合だとデータベース自身の名前になります。

#. **Description**

   ..
       A text description of the service for human reference.

   人が参考にするサービスの説明です。

#. **Label**

   ..
       An optional color code that will be applied to the service in the enStratus console.

   enStratus コンソールのサービスに任意のカラーコードを適用できます。

#. **Service User**

   ..
       The service user will be the user on the server that owns the service.

   これはそのサービスを所有するサーバー上のユーザーとなります。

#. **Backup Frequency**

   ..
       This configuration option specifies the frequency with which enStratus calls the agent
       script called /enstratus/bin/backupService. The function of this script is to call a
       user-configured script called /mnt/services/$serviceID/bin/enstratus-backupDataSource. If
       this script exists, enStratus will execute it and place the resulting file into cloud
       storage. If not, this is a nonoperational event.

   この設定オプションは、enStratus が /enstratus/bin/backupService というエージェントスクリプトを実行する頻度を指定します。このスクリプトの機能は、ユーザが設定した /mnt/services/$serviceID/bin/enstratus-backupDataSource というスクリプトを実行することです。このスクリプトが存在する場合、enStratus はそれを実行し、クラウドストレージにその実行結果のファイルを置きます。そうでない場合は、これは何もしないイベントです。

#. **Service Password**

   ..
       This parameter will become the password that can be used to connect to the data source

   このパラメータは、データソースへの接続に使うパスワードになります。

#. **Custom Configuration**

   ..
       The custom configuration option is a free-form text field that can be used to pass
       information to the enstratus-configure script at the time of service configuration. This
       information will be contained within the enstratus.cfg file.

   カスタム設定オプションは、サービス設定時に enstratus-configure スクリプトに情報を渡すのに使う、自由形式のテキストフィールドです。この情報は enstratus.cfg ファイル内に保存されます。

#. **Data Source Image**

   ..
       The data source image is the database dump file that will be used to initialize the
       database named in the Name in Database field.

   データソースイメージは、データベースフィールドにある名前でデータベースを初期化するのに使うデータベースのダンプファイルです。

#. **Owning Group**

   ..
       The owning group can be assigned to the service if role based access controls are being
       used.

   ロールベースのアクセスコントロールが利用されている場合、所有グループをサービスに割り当てられます。

..
    Dependencies
    ~~~~~~~~~~~~

依存関係
~~~~~~~~

..
   Service, Dependencies

.. figure:: ./images/serviceDependencies.png
   :height: 300px
   :width: 1000 px
   :scale: 50 %
   :alt: Service, Dependencies
   :align: center

   サービス、依存関係

..
    Creating an dependency means establishing a logical connection between services. For
    example, an application service may have a dependency on a database service. Perhaps even
    more meaningful than that, an application service may have a dependency on a database data
    source.

依存関係を作成することは、サービス間の論理的な接続を確立することになります。例えば、アプリケーションサービスは、データベースサービスに依存している可能性があります。さらにもっと重要なことは、アプリケーションサービスがデータベースのデータソースに依存しているかもしれません。

..
    Operationally, if there exists a dependency between two services, when there are changes
    that affect either service such as an auto-recovery or an auto-scaling event, the other
    service is notified by enStratus of this environmental change.

運用上、2つのサービス間に依存関係が存在する場合、自動リカバリーまたは自動スケーリングイベントのような、いずれかのサービスに影響を与える変更があるとき、enStratus がこの環境の変更をその他のサービスに通知します。

..
    This notification process is conducted using the enstratus.cfg file which is passed to all
    affected services in a tier.

この通知処理は、enstratus.cfg ファイルを使い、階層内の影響を受ける全てのサービスに渡されます。

..
    In the figure above, an application service has a dependency on a data source installed on
    a database service. If there is an auto-recovery event on a database server housing the
    data source, the application services that depend on it will be notified when enStratus
    passes in a new enstratus.cfg file to each of them.

上の図では、アプリケーションサービスがデータベースサービスにインストールされているデータソースに依存しています。データソースを保持するデータベースサーバーに自動リカバリーイベントがある場合、それに依存するアプリケーションサービスに対して、enStratus が新しい enstratus.cfg ファイルを各アプリケーションサービスに渡すときに通知されます。

..
    Similarly, when changes such as an auto-recovery or an auto-scaling event occur on servers
    housing the application service, the database service will be notified as well to grant or
    revoke database access as necessary to compensate for changes at the application tier.
    The takeaway message for dependencies is that dependencies establish logical relationships
    between services that ensure the required information is passed when environment
    changes occur such as a scale or recovery of a server that is running an affected service.

同様に、このような自動リカバリーまたは自動スケーリングイベントなどの変更が、アプリケーションサービスを保持するサーバーで発生すると、データベースサービスに通知されて、アプリケーション層での変更を保証するために必要に応じてデータベースアクセスの権限を付与するか、取り消します。このメッセージは、サービス間で論理的な関係を確立する依存関係です。この依存関係は、環境の変更がサーバーで影響を受けた実行中のサービスのリカバリー、またはスケールなどが発生させるとき、必要な情報が渡されるのを保証します。

..
    Delete
    ~~~~~~

削除
~~~~

..
    Deleting a service will remove it from a tier.

サービスを削除すると、階層からそのサービスを削除します。

..
    Versioning
    ~~~~~~~~~~

バージョニング
~~~~~~~~~~~~~~

..
    Maintaining the most recent version of a service is dependent somewhat on the cloud
    provider. If your cloud provider has a concept of attachable block storage devices and
    your services are installed upon one of them that is regularly being snapshotted, it may
    be acceptable to rely on this mechanism for maintaing the most recent software. Update
    your services on the running volumes, and the updates will persist once the next snapshot
    is taken.

サービスの最新バージョンを維持することは、ややクラウドプロバイダーに依存しています。クラウドプロバイダーが取り付け可能なブロックストレージデバイスを持つ場合、定期的にスナップショットが取られたストレージの1つにサービスがインストールされます。これは最新版のソフトウェアをメンテナンスするためにこの仕組みを利用できるかもしれません。動作中のボリューム上のサービスを更新すると、その更新内容は次のスナップショット取得後に永続化されます。

..
    This approach is dependent upon the enStratus auto-recovery and scaling procedures. It is
    advisable to also update the service images that are defined for each service in a tier by
    uploading a new service image via Infrastructure > Service Images and then pointing the
    service definition to the newest version.

この手法は、enStratus の自動リカバリーとスケーリングの手順に依存します。"Infrastructure > Service Images" から新たなサービスイメージをアップロードすることにより、層内の各サービスに定義されているサービスイメージを更新することもお奨めします。その後、サービス定義が最新バージョンを指すようにします。

..
    If your cloud provider has no concept of attachable block storage devices, the only option
    is to take the approach of uploading the new, updated service image via Infrastructure >
    Service images and then pointing the service definition to the newest version.

クラウドプロバイダーが取り付け可能なブロックストレージデバイスを持たない場合、唯一の選択肢は "Infrastructure > Service images" から新規の更新されたサービスイメージをアップロードして、最新バージョンのサービス定義を指すようにしてください。
