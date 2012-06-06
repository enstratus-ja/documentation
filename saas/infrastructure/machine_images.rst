..
    Machine Images
    --------------

.. _saas_machine_images:

マシンイメージ
--------------

..
    Overview
    ~~~~~~~~

概要
~~~~

..
    A machine image is a saved template of a server. Running servers are started from machine images.

マシンイメージは、保存されたサーバのテンプレートです。サーバーの実行は、マシンイメージから起動されます。

..
    If you are going to be utilizing enStratus images to begin your cloud work, please follow this workflow:

enStratus イメージを活用してクラウド環境を構築しようとしているなら、このワークフローに従ってください。

..
    1. Start a server from one of the provided enStratus templates (machine images). 
    2. Next, create a machine image from the server you have started.
    3. Use the resulting image in your work, not the provided enStratus image.

1. 提供された enStratus テンプレート (マシンイメージ) のいずれかを選択してサーバーを開始する
2. 次に開始したサーバからマシンイメージを作成する
3. 提供された enStratus イメージではなく、この作業で作成されたイメージを使う

..
    *Why?*

*なぜ？*

..
    We update the available enStratus images periodically, and when we do, we delete the old
    images to be good stewards of cloud resources. If the backing image of a running server is
    deleted, it can lead to imaging problems going forward. It will not affect the running
    server.

私たちは、定期的に利用可能な enStratus イメージを更新します。その作業を行うときに、クラウドリソースの管財人 (stewards) となるように古いイメージを削除します。実行中のサーバーのバックアップイメージが削除されていると、将来的にイメージに関する問題が発生する可能性があります。これは実行中のサーバーには影響しません。

..
    The functionality included with machine images varies depending on the underlying cloud
    provider. Some cloud providers allow access to a public database of images from which
    private servers can be started. enStratus allows searching and starting of any publicly
    available machine images.

マシンイメージに含まれる機能は、基盤となるクラウドプロバイダーにより異なります。いくつかのクラウドプロバイダーは、プライベートサーバーが起動したところからイメージの公開データベースへのアクセスが許可しています。enStratus は、利用できるマシンイメージを検索して公開されている任意のマシンイメージから開始できます。

..
    Renaming
    ~~~~~~~~

名前変更
~~~~~~~~

..
    To rename a machine image, click on the image name indicated by a brown dashed line. A
    text window will appear. Enter the desired name and select OK.

マシンイメージの名前を変更するには、イメージの名前をクリックします。テキスト画面が表示されます。変更したい名前を入力し、"OK" を選択します。

..
    To change the label color of a machine image, click on the label color and choose the
    desired color from the resulting choices.

マシンイメージのラベルの色を変更するには、ラベルの色をクリックして得られた選択肢の中から希望する色を選択します。

..
    Starting
    ~~~~~~~~

開始
~~~~

..
    To start a server from a machine image, click on the green action button and select
    launch. A dialog box will appear allowing for customization of launch options.

マシンイメージからサーバーを開始するには、アクションボタンをクリックして起動を選択します。ダイアログボックスには、カスタマイズ可能な起動オプションが表示されます。

..
    Some of the launch parameters are governed by the functionality provided for by the
    underlying cloud provider. Most cloud providers allow for customization of the amount of
    hardware (CPU, Memory, storage) provisioned for the server.

起動パラメーターは、基盤となるクラウドプロバイダーから提供される機能により管理されます。ほとんどのクラウドプロバイダーは、サーバにプロビジョニングされるハードウェア (CPU、メモリ、ストレージ) のサイズをカスタマイズできます。

..
    Security Group
    ~~~~~~~~~~~~~~

セキュリティグループ
~~~~~~~~~~~~~~~~~~~~

..
    Security parameters in the form of firewall or security group are also chosen at the time
    of server launch.

また、ファイアウォール形式のセキュリティパラメーターまたはセキュリティグループもサーバ起動時に選択されます。

..
    enStratus layers additional functionality in the form of groups and billing codes into
    server launch for all cloud providers.

enStratus は、グループ形式や課金コードの追加機能を全てのクラウドプロバイダーのサーバーの起動に重ね合わせます。

..
    Key Pair
    ~~~~~~~~

キーペア
~~~~~~~~

..
    Some cloud providers allow servers to be started with a root keypair. enStratus provides
    for this functionality by allowing the user to choose from a set of existing keypairs or
    to create a new keypair at launch.

いくつかのクラウドプロバイダーでは、サーバーがルートキーペアを持って開始できます。enStratus は、ユーザーが既存のキーペアセットから選択したり、起動時に新規キーペアを作成することにより、この機能を提供します。

..
    Volumes
    ~~~~~~~

ボリューム
~~~~~~~~~~

..
    Additionally, through some cloud providers it is possible to specify a volume group to be
    attached, formatted, put into a RAID configuration, and optionally encrypted at launch
    time.

さらに、クラウドプロバイダーによっては、ボリュームグループを指定して接続し、フォーマット、RAID 構成にする、オプションで起動時に暗号化できます。

..
    Once the server is launched, it will usually take less than 20 minutes for the server to
    be ready for use.

サーバが起動すると、通常20分未満でサーバーの準備ができます。

..
    To do:
    #. Launch process
    #. Screenshots

やること:

#. 起動プロセス
#. スクリーンショット
