..
    Add Services
    ------------

サービスの追加
--------------

..
    Adding services to tiers means telling enStratus what service should be installed on
    servers running in the tier. This action only needs to be completed once, no matter how
    many regions/clouds the tier spans.

階層にサービスを追加するというのは、その階層上で実行しているサーバーにどんなサービスがインストールされるかを enStratus へ伝えることになります。この操作は、多くのリージョンやクラウドがその階層にまたがっていたとしても、1回だけ行えば良いです。

..
    To add a service to a tier, select the tier by clicking on it in the designer diagram and
    choose +add service. enStratus will present the list of the services available for
    attaching to the tier. This list should have at a minimum the two services uploaded above. 

階層にサービスを追加するには、デザイナーの図をクリックして階層を選択し、"+add service" を選択します。enStratus は、その階層に追加できるサービスのリストを表示します。このリストには、これまでの作業でアップロードされた (最小) 2つのサービスがあります。

..
    Add Wordpress Service
    ~~~~~~~~~~~~~~~~~~~~~

Wordpress サービスの追加
~~~~~~~~~~~~~~~~~~~~~~~~

..
   Add Service, Wordpress

.. figure:: ./images/addService0.png
   :height: 400px
   :width: 700 px
   :scale: 50 %
   :alt: Add Service, Wordpress
   :align: center

   サービスの追加、Wordpress 

.. note::
   ..
       If there was a previously running deployment where automated backups were made,
       it is also possible to tell enStratus to use a previously generated backup as a service.

       Pretty cool.

   これまでにデプロイメントを行ったことがあれば、自動的にバックアップが作成されているので、作成済みのサービスのバックアップを使うよう enStratus に設定することもできます。

   これは便利でしょう！

..
    Add MySQL Service
    ~~~~~~~~~~~~~~~~~

MySQL サービスの追加
~~~~~~~~~~~~~~~~~~~~

..
   Add Service, MySQL

.. figure:: ./images/addService1.png
   :height: 400px
   :width: 700 px
   :scale: 50 %
   :alt: Add Service, MySQL
   :align: center

   サービスの追加、MySQL 

..
    Associate the wordpress service with the application tier and the mysql service with the
    database tier.

アプリケーション層に Wordpress サービスを、データベース層に mysql サービスを関連付けます。

..
   Services Added

.. figure:: ./images/addService2.png
   :height: 600px
   :width: 2100 px
   :scale: 45 %
   :alt: Services Added
   :align: center

   追加されたサービス

..
    Next, it's time to configure the services. Configuring services means telling enStratus
    what the relationship is, if any, between the services and what information should be
    passed to dynamically configure the service at run time.

次にサービスの設定を行います。サービスの設定は、enStratus にそのサービスの関連性を設定します。つまり、その関連性があると仮定して、サービス間で、実行時、動的にサービスを設定するのに受け渡される情報になります。
