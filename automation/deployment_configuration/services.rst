..
    Services
    --------

サービス
--------

..
    Services are software objects in the form of files, typically tarred, zipped, or gzipped.
    Services must be uploaded to cloud storage before configuring the deployment.

サービスは、ファイル形式のソフトウェアオブジェクトで、通常は tar, zip, gzip などで圧縮されています。デプロイメントを設定する前に、サービスをクラウドストレージにアップロードする必要があります。

..
    A service "image" is a zip (or tar, gz, etc.)  file that can be uploaded to enStratus and
    then selected for use in an automated deployment environment. Services are installed on
    tiers, and have several configuration options, one of which can accomplish the logical
    connections between services known as dependencies.

サービス "イメージ" は zip (または tar や gz など) ファイルで、enStratus にアップロードしてから、自動化したデプロイ環境で使うために選択されます。サービスは、階層にインストールされ、複数の設定オプションを持ち、そのうちの一つは依存関係というサービス間の論理的な関連付けを行います。

..
   Add Service Image

.. figure:: ./images/addServiceImage.png
   :height: 300px
   :width: 600 px
   :scale: 50 %
   :alt: Add Service Image
   :align: center

   サービスイメージの追加

..
    To upload a service image, navigate to Automation > Service Images and select a service
    image from your local file system. Once the service image is finished uploading, it will
    be available as an option for use in a tier.

サービスイメージをアップロードするには、"Automation > Service Images" に移動して、ローカルファイルシステムからサービスイメージを選択します。サービスイメージのアップロードが終了したら、階層で使うオプションとして利用可能になります。
