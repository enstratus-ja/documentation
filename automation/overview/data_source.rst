..
    Add Data Source (optional)
    --------------------------

データソースの追加 (省略可能)
-----------------------------

..
    In some cases, it may be appropriate to connect a datasource to a service. In our example
    deployment, the lower tier is a database tier and the service connected to it is a
    database dump file for MySQL.

場合によっては、サービスにデータソースを関連付けることが適切なときがあります。ここでのデプロイメントの例では、下位層がデータベース層であり、そこに接続されているサービスは MySQL データベースのダンプファイルです。

..
    By connecting a datasource to a service, enStratus knows to first configure the service,
    then pass in the datasource to the service. Proper ordering of operations like that is
    called *orchestration*.

サービスにデータソースを接続することで、enStratus は最初にサービスを設定して、そのサービスにデータソースを渡すことが分かります。このような適切な操作の順序付けを *オーケストレーション* と呼びます。

..
   Data Source Added to Service

.. figure:: ./images/deployment4a.png
   :height: 600px
   :width: 600 px
   :scale: 75 %
   :alt: Data Source Added to Service
   :align: center

   サービスへデータソースの追加
