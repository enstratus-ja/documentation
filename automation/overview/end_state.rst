..
    End State
    ---------

終了状態
--------

..
    A properly configured enStratus deployment is shown below. Each of the functional
    components will be introduced in turn.

適切に設定された enStratus デプロイメントを次に示します。それぞれのコンポーネントの機能を順番に紹介します。

..
   enStratus Deployment

.. figure:: ./images/deployment7.png
   :height: 600px
   :width: 600 px
   :scale: 75 %
   :alt: enStratus Deployment
   :align: center

   enStratus のデプロイメント

..
    The fully operational enStratus deployment is a mechanism for deploying, orchestrating,
    and automating an n-tier application. The above figure shows a 3-tier deployment, running
    in two separate clouds with load balancing and a web application that depends on a
    database. Let's build the deployment from the ground up.

運用に必要な機能を全てもつ enStratus のデプロイメントは、デプロイ、調整、複数階層をもつようなアプリケーションを自動化するための仕組みです。上の図は、3層デプロイメントを表し、2つの異なるクラウドで負荷分散をしながら、1つのデータベースをもつ Web アプリケーションを運用します。基礎的なところからデプロイメントを構築してみましょう。
