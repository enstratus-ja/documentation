..
    Overview
    --------

概要
----

..
    Wordpress is sufficiently complex to demonstrate the full suite of enStratus automation
    capabilities, including the orchestration of a two dependent tiers of scalable servers.

Wordpress は、enStratus の自動化機能の一連のデモを行うのにちょうど良い複雑さをもつプロダクトです。それはスケール可能なサーバーのため、2つの依存層をもつ構造を取ります。

..
    LAMP application stacks are simple to deploy and scale, and enStratus gives you the
    framework to scale and provide for very high-availability applications.

LAMP のアプリケーションスタックは、デプロイやスケールさせることが簡単です。enStratus は、スケールするフレームワークを備え、とても可用性の高いアプリケーションを提供します。

..
    Please follow the Wordpress tutorial at left, you'll be scaling in no time.

では Wordpress のチュートリアルをやってみてください、すぐにスケールさせられることが分かるでしょう。

.. note::
   ..
       Estimated time to complete this tutorial will vary based on several factors such
       as the speed of the cloud provider, and the skill level of the operator.

       New Guy, no SSH skills, no Linux: 1 mo.

       SSH/Firewall skills, cloud-savvy: 2 hrs, maybe less.

       God of the known cloud universe: 1 hr.

   このチュートリアルの予定完了時間は、作業者のスキルレベルや、クラウドプロバイダーの速度といった要因により大きく変わります。

   新人、SSH が分からない、Linux が分からない方: 1ヶ月

   SSH/ファイアウォールを理解してクラウドに精通している方: 2時間以下

   クラウド分野の達人: 1時間

.. warning::
   ..
       The wordpress-demo-prep cookbook and image preparation process described here
       is for tutorial purposes only.

   ここで解説する wordpress-demo-prep のクックブックと準備プロセスの画像は、チュートリアル目的だけのものです。

..
    Purpose
    -------

目的
----

..
    The purpose of this document is to start from scratch and build a deployable enStratus
    application architecture including a Wordpress web application backed by a MySQL database.

このドキュメントの目的は、MySQL データベースを使う Wordpress アプリケーションを、ゼロから始めてデプロイ可能な enStratus アプリケーションアーキテクチャとしてビルドすることです。
