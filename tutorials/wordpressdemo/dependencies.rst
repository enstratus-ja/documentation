..
    Set Dependencies
    ----------------

依存関係の設定
--------------

..
    This step is critical. Dependencies let enStratus know how to *orchestrate* the deployment
    launch and service configuration.

この手順はかなり重要です。依存関係は、enStratus にデプロイメントの起動とサービス設定を *組み合わせる* 方法を伝えます。

..
    For this tutorial, we're going to set a dependency for the wordpress service. It's going
    to depend on the *data source* installed as part of the MySQL service. What this means is
    that at run time, enStratus will ensure:

このチュートリアルでは、Wordpress サービスの依存関係を設定しています。それは MySQL サービスの一部としてインストールされた *データソース* に依存します。これは実行時に enStratus が次のことを保証します。

..
    1. The MySQL service is installed and successfully configured
    2. The datasource is successfully installed on the MySQL service.

1. MySQL サービスをインストールして正常に設定される
2. データソースが MySQL サービス上に正常にインストールされる

..
    and then, and only then will

それから、もう1つだけ行います。

..
    3. The application service be installed, since it *depends* on steps 1 and 2.

3. 手順の1と2に *依存する* アプリケーションサービスがインストールされる

..
    To set up a dependency, select the actions menu on the wordpress service.

依存関係を設定するには、Wordpress サービス上のアクションメニューを選択してください。

..
   Dependency

.. figure:: ./images/dependency0.png
   :height: 500px
   :width: 1900 px
   :scale: 50 %
   :alt: Dependency
   :align: center

   依存関係

..
   Dependency, Add

.. figure:: ./images/dependency1.png
   :height: 300px
   :width: 850 px
   :scale: 50 %
   :alt: Dependency, Add
   :align: center

   依存関係、追加

..
    Choose Target Type: Data Source, and select the previously created data source from the
    menu.

"Target Type:" にデータソースを選択します。このメニューからこれまでの作業で作成したデータソースを選択します。

..
   Dependency, Data Source

.. figure:: ./images/dependency2.png
   :height: 400px
   :width: 850 px
   :scale: 50 %
   :alt: Dependency, Data Source
   :align: center

   依存関係、データソース

..
   Dependency, Saved

.. figure:: ./images/dependency3.png
   :height: 400px
   :width: 850 px
   :scale: 50 %
   :alt: Dependency, Saved
   :align: center

   依存関係、保存
