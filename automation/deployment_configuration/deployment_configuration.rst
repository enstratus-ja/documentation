..
    Deployment Configuration
    ========================

デプロイメントの設定
====================

.. toctree::
   :hidden:

   user_interface
   deployment_management
   load_balancers
   tier
   services
   data_sources
   machine_images
   launch_configuration
   ssl
   backups

.. note::
   ..
       Some of the screenshots may look different than the ones shown here. The
       difference in all cases should be cosmetic and not affect operations.

   スクリーンショットの一部は、ここで説明する内容と違う場合があります。そういった差異は、全て表面的なもので実際の操作に影響はありません。

..
    The purpose of this section is to walk through the deployment configuration options in
    enStratus. 

このセクションの目的は、enStratus のデプロイメント設定のオプションを一通り見てみることです。

..
    In the `Overview <../introduction/overview.html>`_ section, we covered the concepts
    involved with creating an enStratus deployment.

:ref:`overview` のセクションでは、enStratus のデプロイメント作成に関する概念を説明しました。

.. note::
   ..
       Before approaching deployment configuration, you should have in hand the
       following components:

   デプロイメント構成を行う前に、次のコンポーネントを手元に置いておく必要があります:

   ..
      #. Working machine images/templates with the enStratus agent installed and tested.
      #. Service images for each application/database to be installed.

   #. enStratus エージェントでインストールされるのを検証した作業用のマシンイメージやテンプレート
   #. 各アプリケーションやデータベースにインストールされるサービスイメージ

..
    enStratus knows about is the environment in which your application/database runs and it
    will inform your services about that environment. 

enStratus は、アプリケーションやデータベースが実行される環境を把握していて、その環境に関する情報をサービスに伝えます。

..
    enStratus gives you all the tools to deploy and manage a fully automated environment.

enStratus は、完全に自動化された環境をデプロイして管理するための全てのツールを提供します。
