..
    Data Sources
    ------------

データソース
------------

..
    To upload a data source into enStratus, navigate to Automation > Data Source Images and
    select add data source.

enStratus にデータソースをアップロードするには、"Automation > Data Source" に移動して、データソースの追加を選択します。

..
    A data source can be a database backup file. For example, for a MySQL database, the data
    source may be represented by a file with a .sql extension. This file is downloaded from
    cloud storage during the start and configuration of a service that has associated a data
    source.

データソースは、データベースのバックアップファイルにもなります。例えば、MySQL データベースのデータソースは ".sql" の拡張子を持つファイルです。このファイルは、データソースに関連付けられたサービスの起動時や設定時にクラウドストレージからダウンロードされます。

..
   Add Data Source

.. figure:: ./images/addDataSource.png
   :height: 300px
   :width: 600 px
   :scale: 50 %
   :alt: Add Data Source
   :align: center

   データソースの追加

..
    Using
    ~~~~~

使用要項
~~~~~~~~

..
    Data sources are used when configuring a service. More is said about this in the
    section on Tiers, which hold services. A data source is a database backup file, typically
    in the form of a "dump" file of the form database1.sql. Data sources, like
    services, should be uploaded into cloud storage before configuring the deployment.

サービスを設定するときにデータソースを使います。さらに詳細な説明は、サービスを保持する階層のセクションをご覧ください。データソースは、データベースのバックアップファイルです。通常は "database1.sql" といった "dump" ファイルの形態になります。サービスと同様に、データソースはデプロイメントを設定する前にクラウドストレージにアップロードしておく必要があります。
