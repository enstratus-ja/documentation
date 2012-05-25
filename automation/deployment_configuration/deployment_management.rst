..
    Deployment Management
    ---------------------

デプロイメントの管理
--------------------

..
   Deployment Management

.. figure:: ./images/deploymentManagement.png
   :height: 500px
   :width: 1300 px
   :scale: 60 %
   :alt: Deployment Management
   :align: center

   デプロイメントの管理

..
    Deployment management and configuration starts  with the options shown in the figure
    above.

デプロイメントの管理や設定は、上の図で表示されるオプションを選択するところから始めます。

#. **Name**

   ..
       The name of the deployment is simply the logical name that will be presented in the
       enStratus console. 

   デプロイメントの名前は、enStratus コンソール上で表示されるだけの論理的な名称です。

#. **Label**

   ..
       An optional color code may be applied to the deployment.

   デプロイメントに適用できる任意のカラーコードです。

#. **Deployment Type**

   ..
       The deployment type has two options:
       
       * Dedicated. 

         A dedicated deployment will track all deployments costs against the same
         billing code.

       * Shared. 

         A shared deployment will track deployment costs against multiple billing codes.
         If a shared deployment is chosen, billing code usage will be tracked at the service level.
         
   デプロイメント種別には、2つのオプションがあります。

   * 専用

     専用デプロイメントは、同じ課金コードに対して全てのデプロイコストを監視します。

   * 共用

     共有デプロイメントは、複数の課金コードに対してデプロイコストを監視します。
     共有デプロイメントを選択した場合、課金コードの用途として、サービスレベルで監視します。

#. **Disaster Recovery Storage**

   ..
       Disaster recovery storage specifies a cloud storage option for backup files. It is
       possible to run all or parts of a deployment in one cloud while performing backups via
       /enstratus/bin/backupService to another cloud altogether for disaster recovery purposes.

   ディザスタリカバリストレージは、バックアップのためにクラウドストレージオプションを指定します。ディザスタリカバリに /enstratus/bin/backupService 経由で他のクラウドへフルバックアップの実行中も、そのクラウド内でデプロイメントの全処理、または一部の処理を実行できます。

#. **Billing Code**

   ..
       The billing code is the code against which all deployment charges will be made.

   課金コードは、全てのデプロイ料金の対象となるコードです。

#. **Owner**

   ..
       The owner specifies an optional owner for the deployment so that role based access
       controls may apply to the deployment.

   ロールベースのアクセスコントロールをデプロイメントに適用したい場合もあるので、デプロイメントの所有者を選択して指定します。

#. **Description**

   ..
       The description is a free form text field for describing the deployment.

   デプロイメントを説明するのに自由記述できるテキストフィールドです。

..
    Backup/Maintenance
    ~~~~~~~~~~~~~~~~~~

バックアップ/メンテナンス
~~~~~~~~~~~~~~~~~~~~~~~~~

..
   Backup and Maintenance

.. figure:: ./images/backupMaintenance.png
   :height: 600px
   :width: 1500 px
   :scale: 50 %
   :alt: Backup and Maintenance
   :align: center

   バックアップとメンテナンス

..
    The backup options designate the times when enStratus will peform backups such as
    snapshots of attached volumes or service level backups via the agent script
    /enstratus/bin/backupService.

バックアップオプションでは、enStratus がいつバックアップを実行するかを指定します。これは /enstratus/bin/backupService エージェントスクリプトによるサービスレベルのバックアップ、または接続したボリュームのスナップショットといったものです。

..
    Manage Servers/Services
    ~~~~~~~~~~~~~~~~~~~~~~~

サーバー/サービスの管理
~~~~~~~~~~~~~~~~~~~~~~~

..
    These tabs display an aggregated view of all servers running in the deployment and all of
    the services installed on the deployment.

デプロイメントで実行中の全サーバーとインストールされた全サービスを集約して複数タブで表示します。
