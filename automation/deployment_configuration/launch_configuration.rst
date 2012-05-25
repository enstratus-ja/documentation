..
    Launch Configuration
    --------------------

起動構成
--------

..
    A launch configuration is a definition that governs the resources provisioned to support a
    virtual machine. At one level, this is roughly analogous to the size definitions provided
    for by some clouds, such as in Amazon AWS small, medium, large, etc.  For enStratus a
    launch configuration includes this definition, but goes beyond to include attaching,
    raiding, and encrypting volumes as well as the firewall into which the server is started.

起動構成は、仮想マシンに対応するようにプロビジョニングされたリソースを管理する定義です。1つのレベルでは、Amazon AWS の small, medium, large といった、複数のクラウドによるサイズ定義と大雑把に類似しています。enStratus の起動構成はこの定義を含みますが、さらにサーバーの起動時にファイアウォール同様、ボリュームの暗号化、RAID 設定、接続も含みます。

..
   Launch Configuration

.. figure:: ./images/launchConfigurationHighlighted.png
   :height: 600px
   :width: 500 px
   :scale: 50 %
   :alt: Launch Configuration
   :align: center

   起動構成

..
    Manage Launch Configuration, General Information
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

起動構成の管理、全般的な情報
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
   Launch Configuration (General Information)

.. figure:: ./images/launchConfigurationGeneralInformation.png
   :height: 450px
   :width: 1600 px
   :scale: 50 %
   :alt: Launch Configuration (General)
   :align: center

   起動構成 (全般的な情報)

#. **Server Name Template**

   ..
       The server name template controls the name that is applied to servers that are started
       according to the launch configuration. There are two approaches to naming servers as part
       of the launch configuration.

   サーバー名テンプレートは、起動構成に従って開始されたサーバーに適用する名前を制御します。起動構成の一部として、サーバーの名前付けには2つの方法があります。

   ..
       The first approach is to just hard code a value for this field. The implications of this
       are if the tier scales to include many servers, they will all be named the same thing,
       which is allowed, and not always desirable.

   最初のアプローチは、このフィールドに単純に名前をハードコードするだけです。これは、この階層が多くのサーバーをもつようにスケールアウトするなら、それらは全て同じ名前が付けられます。但し、必ずしもその名前が望ましいというわけではありません。

   ..
       The second approach is to use parameters as shown in the figure above. The available
       parameters are:

   上の図にあるように、2番目の方法は、次のパラメーターを使います。利用可能なパラメータは次の通りです:

   ..
       * {tier} name of the tier this server is running in.
       * {group} currently resolves to tier name, for backwards compatibility.
       * {count} count of this server (sequential numbering from 1 for a tier.)
       * {role} one of: CLUSTER NODE, INDEPENDENT NODE, MASTER, REPLICANT, STANDALONE (converted
         to lowercase string)
       * {type} one of: LOAD, SERVICE, CLUSTERED DATABASE, REPLICATED DATABASE, UNKNOWN
         (converted to lowercase string)
       * {zone} the provider zone ID where the server is running.
       * {dc} resolves the same as zone above.
       * {region} the provider region ID where the server is running.
       * {ip} reserved address (public IP) of the server.
       * {year} launch year of the server.
       * {day} launch day of the server.
       * {hour} launch hour of the server.
       * {minute} launch minute of the server.

   * {tier} このサーバーを実行中の階層名
   * {group} 後方互換性のために、現在のところ階層名を解決する
   * {count} このサーバーの連番 (階層ごとに1からの連番)
   * {role} CLUSTER NODE, INDEPENDENT NODE, MASTER, REPLICANT, STANDALONE のうち1つ (小文字に変換される)
   * {type} LOAD, SERVICE, CLUSTERED DATABASE, REPLICATED DATABASE, UNKNOWN のうち1つ (小文字に変換される)
   * {zone} サーバを実行中のプロバイダーゾーン ID
   * {dc} 上のゾーンと同様に解決する
   * {region} サーバを実行中のプロバイダーリージョン ID
   * {ip} サーバーの予約アドレス (パブリック IP)
   * {year} サーバの起動した年
   * {day} サーバの起動した日
   * {hour} サーバの起動した時間
   * {minute} サーバの起動した分

   ..
       This approach has the advantage of uniquely naming servers as they join/leave a tier in an
       intelligent manner.

   このやり方は、合理的な方法で階層に追加/削除するサーバーに一意な名前を付けるという利点があります。
   
#. **Recovery Point**

   ..
       The recovery point parameter sets the amount of time enStratus will wait to begin a
       recovery event of a failed server. A server is assumed to have failed if the agent is
       unreachable, and the server is un-ping-able, or the server has stopped altogether and is
       no longer being counted in the min/max.

   リカバリーポイントのパラメーターは、停止したサーバーのリカバリーイベントを enStratus が開始するまでの待機時間を設定します。このエージェントが通信できなくなったら、サーバーが停止したと仮定されます。そして、このサーバは ping 応答がない、またはサーバーが完全に停止して、その後は min/max のサーバーとして数えなくなります。

#. **Use Encryption**

   ..
       This setting determines whether volumes attached to servers are encrypted. This option is
       currently only meaningful for Linux-based servers that can employ the Linux Unified Key
       Setup. This type of encryption is file-system based encryption.

   この設定は、サーバーに接続されたボリュームが暗号化されているかどうかを決定します。このオプションは、現在のところ、Linux の統一キー設定を採用する Linux ベースのサーバーのみ意味があります。この暗号化種別は、ファイルシステムベースの暗号化です。

#. **Server Type**

   .. There are five options for Server Type:

   サーバー種別には、5つのオプションがあります:

   ..
       * Load balancer. This option specifies a launch configuration as a load balancer so
         that servers in this tier will be treated as such.

   * ロードバランサー: このオプションは、この層のサーバーをロードバランサーとして扱うように起動構成を指定します。

   ..
       * Service General Service. This option identifies the servers governed by this launch
         configuration as a generic service such as a web application.

   * 一般サービス: このオプションは、この起動構成で管理するサーバーが Web アプリケーションのような汎用サービスを提供するものであると識別します。

   ..
       * Clustered Database A clustered database is a database that is not using replication and
         is therefore treated as an independent entity.

   * クラスタ化されたデータベース: これはレプリケーションを使わないデータベースであり、独立した存在として扱われます。

   ..
       * Replicated Database A replicated database is a database that is set up to perform
         replication.

   * レプリケートされたデータベース: これはレプリケーションを実行するように設定されているデータベースです。

   ..
       * Unknown Similar to a service, this is a generic entry for a service.

   * 未知のサービス: これは任意のサービス向けの汎用的な設定です。

#. **Snapshot Frequency**

   ..
       This parameter sets the frequency with which enStratus automatically performs snapshots of
       the attached volume. It is important to note that although there may be multiple servers
       running as part of a tier, each with its own volume attached, enStratus will only snapshot
       one of the volumes.

   このパラメータは、enStratus が接続されたボリュームのスナップショットを自動的に取得する頻度を設定します。階層の一部として複数のサーバが実行されており、それぞれのサーバーが独自のボリュームに接続されていたとしても、enStratus はそのうちの1つのボリュームだけスナップショットを取ることに注意してください。

   ..
       This highlights an important architectural consideration. Each server running in a tier
       should be identical, as should the attached volumes. If variation is required in the
       architecture between servers, that is an indication that an extra tier should be
       configured.

   これはアーキテクチャを検討する上でとても重要であると言えます。階層で実行中の各サーバーは同一であり、接続されたボリュームも同様にする必要があります。サーバー間のアーキテクチャに変更が必要なら、追加の階層を設けるべきだという兆候です。

   ..
       Take care not to set the snapshot frequency too low. Snapshots lock the file system until
       they are complete, which can impact your application performance. Additionally, most cloud
       providers limit the number of snapshots that can be stored and if the setting is to a high
       frequency, this limit may result in errors. Typically one snapshot per day is sufficient
       for most applications.

   あまり頻繁にスナップショットを取る設定をしないように注意してください。スナップショットが完了するまでファイルシステムをロックします。これはアプリケーションのパフォーマンスに影響を与えることがあります。また、ほとんどのクラウドプロバイダーは、スナップショットの保存可能数を制限します。その設定を高頻度にすると、この制限を超えてエラーになる可能性があります。通常、ほとんどのアプリケーションは1日に1つのスナップショットで十分です。

..
    Machine Images
    ~~~~~~~~~~~~~~

マシンイメージ
~~~~~~~~~~~~~~

..
   Launch Configuration Machine Images

.. figure:: ./images/launchConfigurationMachineImage.png
   :height: 500px
   :width: 1900 px
   :scale: 50 %
   :alt: Launch Configuration Machine Images
   :align: center

   起動構成のマシンイメージ

#. **Primary Machine Image**

   ..
       The primary machine image specifies the machine image that enStratus will use to start
       servers in the tier.

   プライマリマシンイメージは、enStratus が階層でサーバを起動するのに使うマシンイメージを指定します。

#. **Primary Product**

   ..
       The primary product will contain a list of options that is very cloud-specific. The figure
       shows an option that is specific to the AWS EC2 provider. If you are using a different
       cloud provider you will see other options present here.

   プライマリプロダクトは、クラウド固有のオプションリストです。この図は AWS EC2 プロバイダー固有のオプションを表示します。別のクラウドプロバイダーを使っている場合は、別のオプションがここに表示されます。

#. **Secondary Machine Image**

   ..
       The secondary machine image is a machine image of an optionally unique definition that 
       enStratus will use to launch subsequent servers from the secondary machine image definition.

   セカンダリマシンイメージは、enStratus が後続サーバーを起動するのに使う任意の固有定義をもつマシンイメージです。

   ..
       The most logical implementation for using a secondary machine image is in the case of
       replicated databases. The primary machine image would be used by enStratus to launch the
       master database and all subsequent servers would function as slaves using the secondary
       machine image.

   セカンダリマシンイメージを使う最も論理的な実装例は、レプリケートされたデータベースです。enStratus によりマスターデータベースを起動するためにプライマリマシンイメージが使われます。そして、後続の全サーバーが、セカンダリマシンイメージを使ってスレーブとして機能します。

#. **Secondary Product**

   ..
       The secondary product defines the amount of virtual hardware provisioned in the same
       manner as the primary product.

   セカンダリプロダクトは、プライマリプロダクトと同様にプロビジョニングされた仮想ハードウェアのサイズを定義します。

Volumes
~~~~~~~

.. note::
   .. 
       The volumes option is only present if the cloud provider features block storage.

   ボリュームオプションは、クラウドプロバイダーがブロックストレージを備えている場合にのみ表示します。

..
   Launch Configuration, Volumes

.. figure:: ./images/launchConfigurationVolumes.png
   :height: 400px
   :width: 2400 px
   :scale: 40 %
   :alt: Launch Configuration, Volumes
   :align: center

   起動構成、ボリューム

..
    The volumes specification determines the number and size of volumes that will be attached
    to servers in the tier. The option to encrypt these volumes is specified as part of the
    general configuration above.

ボリューム設定は、階層のサーバーに接続されるボリュームの数とサイズを決定します。これらのボリュームの暗号化オプションは、全般設定の項目で指定します。

..
   Launch Configuration, Firewalls

.. figure:: ./images/launchConfigurationFirewalls.png
   :height: 400px
   :width: 2400 px
   :scale: 40 %
   :alt: Launch Configuration, Firewalls
   :align: center

   起動構成、ファイアウォール

..
    The firewall definition specifies the firewall into which servers in this launch
    configuration are started.

ファイアウォール設定は、この起動構成のサーバー内で開始するファイアウォールを指定します。

..
    Manage Servers, Servers
    ~~~~~~~~~~~~~~~~~~~~~~~

サーバー管理、サーバー
~~~~~~~~~~~~~~~~~~~~~~

..
    Selecting this tab will show the servers running as part of the selected launch
    configuration.

このタブを選択すると、選択した起動構成で実行中のサーバーが表示されます。
