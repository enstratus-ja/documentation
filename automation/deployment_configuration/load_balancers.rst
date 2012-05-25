..
    Load Balancers
    --------------

ロードバランサー
----------------

..
    A load balancer balances traffic typically to multiple application servers. enStratus
    supports multiple types of load balancers through different mechanisms.

ロードバランサーは通常、複数のアプリケーションサーバーにトラフィックを分散させます。enStratus は、異なる仕組みをで複数のタイプのロードバランサーをサポートします。

..
   Load Balancer

.. figure:: ./images/loadBalancer.png
   :height: 400px
   :width: 400 px
   :scale: 50 %
   :alt: Load Balancer
   :align: center

   ロードバランサー

..
    Physical
    ~~~~~~~~

物理的
~~~~~~

..
    A virtual machine based load balancer can use HA-Proxy, mod-jk, or zeus as a load
    balancer. When a service is connected to a virtual machine based load balancer, The agent
    script /enstratus/bin/startProxy is used to signal the load balancer that a new
    application server has joined the pool. The agent script /enstratus/bin/stopProxy is used
    to signal the load balancer that an application server has left the pool.

仮想マシンベースのロードバランサーとしては、HA-Proxy, mod-jk, zeus が使えます。サービスが仮想マシンベースのロードバランサーに接続されている場合、エージェントスクリプト /enstratus/bin/startProxy は、新しいアプリケーションサーバーがプールに追加されたことをロードバランサーに通知するのに使われます。また、エージェントスクリプト /enstratus/bin/stopProxy は、アプリケーションサーバーがプールから削除されたことをロードバランサーに通知するのに使われます。

..
    Virtual (Example: ELB)
    ~~~~~~~~~~~~~~~~~~~~~~

仮想 (例: ELB)
~~~~~~~~~~~~~~

..
    Some cloud providers support service-based load balancing in the from of a virtual load
    balancer. In AWS, this is called an Elastic Load Balancer (ELB). In cloudstack (cloud.com)
    clouds, sometimes this is called a Router Virtual Machine (RVM). If your cloud provider
    has this concept with API support, enStratus can support it.

クラウドプロバイダーには、仮想ロードバランサーの形態でのサービスベースの負荷分散に対応しています。AWS では、これを弾力性のあるロードバランサー（ELB）と呼びます。CloudStack (cloud.com) のクラウドでは、ルーター仮想マシン (RVM) と呼ぶこともあります。もしお使いのクラウドプロバイダーが API と共にこの概念に対応しているなら、enStratus はその機能をサポートできます。

..
    If a service is tied to a virtual load balancer, the server upon which that service runs
    will be added to and dropped from the load balancer via api calls. Furthermore, if the
    load balancer is set to balance traffic to a specific zone or zones, enStratus will ensure
    that your application servers only start in those zones.

サービスが仮想ロードバランサーに接続されているなら、そのサービスを実行しているサーバーは、ロードバランサーに追加したり、削除したりといったことを API 経由で行えます。さらに、ロードバランサーが特定ゾーン、またはゾーンへのトラフィックを分散するように設定されているなら、enStratus はアプリケーションサーバーをこれらのゾーンでのみ起動することを保証します。

..
    Load balancing is connected to the deployment at the *service* level with enStratus. An
    important point which will be illustrated shortly.

負荷分散は、enStratus と共に *サービス* レベルでのデプロイメントに接続されます。重要なポイントを手短に説明します。

.. note::
   ..
      It is possible to associate multiple load balancers with a deployment. This
      feature is useful when working in a cross-cloud or in a massively scaled, geographically
      disperse environment.

   デプロイメント時に複数のロードバランサーを関連付けできます。この機能は、クラウドをまたがる、大規模にスケールさせる、地理的に分散した環境を連携させるのに便利です。

..
   Adding a Load Balancer

.. figure:: ./images/addLoadBalancer.png
   :height: 600px
   :width: 1100 px
   :scale: 50 %
   :alt: Adding a Load Balancer
   :align: center

   ロードバランサーの追加

..
    Load balancer configuration options are:

ロードバランサーの設定オプションです:

#. **Account**

   ..
       The account specifies the account to which the load balancer is provisioned. If the
       administrator is a member of multiple accounts, there may be multiple options here.
       One possibility here is to have a load balancer span across several clouds. For example, a
       load balancer may be provisioned into a cloud.com cloud with application servers in both
       EC2 and in cloud.com

   アカウントには、ロードバランサーをプロビジョニングするアカウントを指定します。この管理者が複数アカウントのメンバーなら、そこに複数のオプションが表示されるかもしれません。ここでロードバランサーが複数のクラウドにまたがっている可能性があります。例えば、EC2 と cloud.com の両方にアプリケーションサーバーをもつ cloud.com のクラウド内でロードバランサーがプロビジョニングされるかもしれません。

#. **Region**

   ..
       It is possible to have a load balancer span regions within a cloud. For example, the EC2
       cloud has at the time of this writing 5 regions.

   クラウド内のリージョンをまたがってロードバランサーを設定できます。例えば、EC2 のクラウドには、執筆時点で5つのリージョンがあります。

#. **Scope**

   .. The scope parameter has three different settings:

   スコープパラメータには、3つの異なる設定があります:

  * **Global**

    ..
        A global setting will cause the load balancer to balance across regions, but is
        nonsensical for virtual load balancing offerings such as an ELB.

    グローバル設定は、ロードバランサーにリージョン間でバランスを取るようにします。但し、ELB などの仮想ロードバランシングオファリングには無意味です。

  * **Regional**

    ..
        A regional load balancer will balance traffic to only one region, and evenly
        to all data centers within that region.

    リージョンに属するロードバランサーは、1つのリージョン内でのみトラフィックを分散し、そのリージョン内の全てのデータセンターに対して均等にします。

  * **Data Center** 

    ..
        A data center setting will balance to specific data centers. This type of
        load balancing only makes sense for virtual load balancing offerings such as an ELB where
        data centers (zones) can be specified prior to launch. This setting is non-sensical for
        VM-based load balancing where no such option exists.

    データセンターの設定は、特定のデータセンターに分散させます。この種の負荷分散は、起動前にデータセンター (ゾーン) を指定できる ELB のような仮想ロードバランシングオファリングでのみ有効です。この設定は、そういったオプションがない仮想マシンベースの負荷分散では無効です。

..
    There are three types load balancer that can be provisioned within enStratus:

enStratus 内でプロビジョニングできるロードバランサーは3種類あります。

#. **Cloud**

   ..
       A cloud load balancer is a virtual load balancer such as an Amazon EC2 Elastic
       Load Balancer. If the cloud provider has no such concept, there will be no option
       presented.

   クラウドロードバランサーは、Amazon EC2 Elastic Load Balancer のような仮想ロードバランサーです。クラウドプロバイダーがこの概念に対応していないなら、オプションは表示されません。

   ..
       In order for this option to be presented, a cloud load balancer must have already been
       provisioned.

   オプションが表示されるには、クラウドロードバランサーが先にプロビジョニングされている必要があります。

#. **VM Dynamic** 

   ..
       A VM Dynamic load balancer means that at the time of deployment start,
       enStratus will provision a virtual server from the specified template with the appropriate
       resources, and launch it into the specified fireall. If a VM Dynamic load balancer is
       provisioned, it will benefit from auto-recovery.

   VM ダイナミックロードバランサーは、デプロイメントの開始時に、enStratus が、適切なリソースと共に指定したテンプレートから仮想サーバーをプロビジョニングして、指定したファイアウォール内にそのサーバーを起動することを指します。VM のダイナミックロードバランサーがプロビジョニングされると、自動リカバリーの利点もあります。

#. **VM Static** 
   
   ..
       A VM Static load balancer will "convert" an existing virtual machine
       into a load balancer by calling the /enstratus/bin/startProxy script on the VM specified
       at the appropriate time.

   VM スタティックロードバランサーは、VM 上の /enstratus/bin/startProxy スクリプトを適切なときに実行することで、既存の仮想マシンをロードバランサーに "変換" します。

   ..
       Currently, VM Static load balancer do not benefit from auto-recovery. If auto-recovery is
       desired, use a VM Dynamic load balancer instead.

   今のところ、VM スタティックロードバランサーには、自動リカバリーの利点はありません。自動リカバリーが必要なら、代わりに VM ダイナミックロードバランサーを使ってください。
