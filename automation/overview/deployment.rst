..
    The Deployment
    --------------

デプロイメント
--------------

..
   enStratus Deployment

.. figure:: ./images/deployment1.png
   :height: 600px
   :width: 600 px
   :scale: 75 %
   :alt: enStratus Deployment
   :align: center

   enStratus のデプロイメント

..
    An enStratus deployment is a container enStratus uses to manage all of moving parts of an
    aribtrarily complex application. The resources running in the deployment are subject to
    the constraints the deployment architect places on it, such as when to scale, when backups
    are run, and what relationships exist between deployment components.

enStratus のデプロイメントは、複雑なアプリケーションの流動的な全要素を管理するために使うコンテナーです。デプロイメントで実行されるリソースは、いつスケールするか、いつバックアップするか、デプロイメントコンポーネント間にどんな関連があるかといったデプロイメントアーキテクト上の制約を受けます。

..
    The deployment itself needs only a name, this initializes the deployment environment for
    the rest of the build. The first component added to this deployment is called a tier.

デプロイメント自体は名前だけを必要とし、残りはビルドするためにデプロイメント環境を初期化します。このデプロイメントに最初に追加されるコンポーネントを階層と呼びます。

..
    A place holder for adding a load balancer is automatically generated.

ロードバランサーを追加するためのプレースホルダーが自動的に生成されます。
