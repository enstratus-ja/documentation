..
    Configure Launch Configuration
    ------------------------------

起動構成の構成
--------------

..
    The next and final thing to do is to configure virtual resources to use in the deployment.
    By now, the imaged we prepared earlier should be ready for use in the launch
    configuration.

この次に行う最後の作業は、デプロイメントを使うために仮想リソースを設定することです。そろそろ起動構成で使うために最初に用意したイメージの利用を準備します。

..
    In these steps, we'll tell enStratus what Image to use when starting servers, along with
    what firewall into which the servers will be started.

これらの手順では、起動するサーバー内のファイアウォールと共に、サーバーの起動時にどのイメージを使うかを enStratus へ伝えます。

.. note::
   ..
       For this tutorial, we'll be using the same image for both launch configurations.
       In practice, this would probably not be the case, as a dedicate image would be used to
       support the application, and likewise the database.

  このチュートリアルでは、両方の起動構成に同じイメージを使っています。実際には、そのアプリケーションやデータベースに対応したそれぞれの専用イメージとなり、このようにはならないでしょう。

..
    Set an image for use in each of the launch configurations, as shown:

次のように起動構成に使うイメージを設定してください:

..
    Wordpress Launch Configuration
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Wordpress の起動構成
~~~~~~~~~~~~~~~~~~~~

..
   Launch Configuration, Wordpress

.. figure:: ./images/lc1.png
   :height: 900px
   :width: 1300 px
   :scale: 50 %
   :alt: Launch Configuration, Wordpress
   :align: center

   起動構成、Wordpress

..
    Once the initial launch configurations are set, click on the launch configuration, scroll
    to the bottom, and use the previously created firewall.

初期起動構成を行ったら、起動構成をクリックし、下の方へスクロールして、これまでに作成したファイアウォールを使います。

..
   Launch Configuration, Edit Wordpress

.. figure:: ./images/lc3.png
   :height: 500px
   :width: 2100 px
   :scale: 50 %
   :alt: Launch Configuration, Wordpress
   :align: center

   起動構成、Wordpress の編集

..
    MySQL Launch Configuration
    ~~~~~~~~~~~~~~~~~~~~~~~~~~

MySQL 起動構成
~~~~~~~~~~~~~~

..
   Launch Configuration, MySQL

.. figure:: ./images/lc2.png
   :height: 1100px
   :width: 1300 px
   :scale: 50 %
   :alt: Launch Configuration, MySQL
   :align: center

   起動構成、MySQL

..
    Once the initial launch configurations are set, click on the launch configuration, scroll
    to the bottom, and use the previously created firewall.

初期起動構成を行ったら、起動構成をクリックし、下の方へスクロールして、これまでに作成したファイアウォールを使います。

..
   Launch Configuration, Edit MySQL

.. figure:: ./images/lc3.png
   :height: 500px
   :width: 2100 px
   :scale: 50 %
   :alt: Launch Configuration, MySQL
   :align: center

   起動構成、MySQL の編集
