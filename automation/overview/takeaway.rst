..
    Takeaway Points
    ---------------

習得内容の要点
--------------

..
    #. A deployment is a logical grouping of tiers, services, and launch configurations. Resources provisioned as part of a deployment are "special" in the sense that they are subject to the governing rules set by the user.
    #. Tiers are logical groupings of servers.
    #. Services are software packages that are tied to tiers. 
    #. Services can have datasources passed to them and can depend on each other, or each other's datasources.
    #. Dependencies tell enStratus how to orchestrate service installation and what information is appropriate to pass to each VM.
    #. Launch Configurations define the size of the VM, volumes, configuration management, and firewalls for each server.
    #. As servers are started, enStratus orchestrates the installation of services and datasources according to their dependency relationships.

#. デプロイメントは、起動構成、サービス、階層の論理的なグループです。デプロイメントの一部としてプロビジョニングされたリソースは、ユーザーが管理するルールセットによる特別なものです。
#. 階層は、サーバーの論理的なグループです。
#. サービスはソフトウェアパッケージであり、階層に関連付けられます。
#. サービスは、相互に渡せるデータソースをもち、他のサービス、または他のデータソースに依存します。
#. 依存関係は、サービスのインストールを調整し、VM に適切な情報を渡せるよう enStratus に伝えます。
#. 起動設定は、VM のサイズ、ボリューム、構成管理、各サーバーのファイアウォールを定義します。
#. サーバーを起動すると、enStratus はサービスのインストールと依存関係に関連するデータソースを調整します。
