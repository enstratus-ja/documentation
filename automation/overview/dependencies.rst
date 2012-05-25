..
    Establish Dependencies
    ----------------------

依存関係の確立
--------------

..
    A dependency is a logical connection between services that tells enStratus about the
    relationship two services have. Here, we've established a dependency relationship between
    the top (application) tier and the database service's datasource. 

依存関係は、サービス間の論理的なつながりであり、2つのサービス間の関係を enStratus に伝えます。ここでは、上位 (アプリケーション) 層とデータベースサービスのデータソース間の依存関係を確立しました。

..
    A special type of dependency is established for the application service to the load
    balancer as well.

ロードバランサーに対するアプリケーションサービスの特殊な依存関係の確立も同様です。

..
   Establish Dependencies

.. figure:: ./images/deployment5.png
   :height: 600px
   :width: 600 px
   :scale: 75 %
   :alt: Establish Dependencies
   :align: center

   依存関係の確立

..
    Establishing dependencies tells enStratus how to orchestrate the deployment of the
    services. Given the dependency relationships described here, the following events will
    happen:

依存関係を確立することで、enStratus はサービスのデプロイメントをどう調整するかが分かります。ここで説明する所定の依存関係は、次のイベントを発生させます:

..
    #. Service installed on the Database Tier
    #. Datasource installed on the Database Service
    #. Service installed on the Application Tier.
    #. enStratus passes information to the database server so it can grant access to the application servers.
    #. enStratus passes information to every server in the application tier about how to find the datasource.
    #. enStratus passes information to the load balancer about each application node.

#. データベース層でサービスがインストールされる
#. データベースサービスにデータソースがインストールされる
#. アプリケーション層でサービスがインストールされる
#. enStratus は、データベースサーバーに情報を渡し、アプリケーションサーバーに対するアクセス権を付与できる
#. enStratus は、アプリケーション層の全てのサーバーにデータソースの検出方法についての情報を渡す
#. enStratus は、各アプリケーションノードに関する情報をロードバランサーに渡す

..
    At this point, the deployment is nearly configured. We have yet to tell enStratus about
    the servers that will house the services.

この時点でデプロイメントの設定がほぼ完了しました。残りの作業として、サービスを格納するサーバーを enStratus に設定する必要があります。
