..
    Make Image
    ----------

イメージの作成
--------------

..
    To make an image, start with a generic EC2 image from `Alestic <http://alestic.com/>`_.
    Eric's team has recently begun publishing only 64-bit images. Any generic ubuntu image
    *should* work, but this tutorial has only been tested with images from Alestic.

イメージを作るには `Alestic <http://alestic.com/>`_ から汎用的な EC2 イメージを使います。Eric のチームは最近64ビットイメージのみを公開するようになりました。汎用的な Ubuntu イメージなら何であれ *動くはず* ですが、このチュートリアルでは、Alerstic のイメージのみをテストしました。

..
   Search for AMI

.. figure:: ./images/ami0.png
   :height: 400px
   :width: 1800 px
   :scale: 50 %
   :alt: Search for AMI
   :align: center

   AMI の検索

..
    1. Start the image as a VM, choose a large product size, not t1.micro for best results.
       Also, generate and use an SSH key during the launch.

1. VM としてのイメージからです。大きなプロダクトサイズを選択してください。少なくとも t1.micro は適切ではありません。また、起動中に利用する SSH キーを生成しておいてください。

..
   Launch, General Information

.. figure:: ./images/ami1.png
   :height: 600px
   :width: 850 px
   :scale: 50 %
   :alt: Launch, General Information
   :align: center

   起動画面の全体情報

..
    Save the key and chmod it

生成したキーを保存して chmod します。

.. code-block:: bash

   chmod 600 demoKey

..
   Launch, Create/Use Key

.. figure:: ./images/ami3.png
   :height: 450px
   :width: 1200 px
   :scale: 50 %
   :alt: Launch, Create/Use Key
   :align: center

   起動画面のキーの生成と利用

..
    2. While the image launches, open the firewall so you can access port 22 from your
       location.
    3. Once the VM is started, copy the wordpress-demo-prep.tar.gz file to the instance.
       The command to do so will be something of the form:

2. イメージの起動中に、作業しているところから22番ポートへアクセスできるようにファイアウォールを設定してください。
3. VM を起動したら、wordpress-demo-prep.tar.gz ファイルをそのインスタンスへコピーします。この作業を行うには次のコマンドを実行します。

.. code-block:: bash

   scp -i demoKey wordpress-demo-prep.tar.gz ubuntu@ip.of.running.instance:~

..
    4. Next, ssh onto the running instance, and take root:

4. 次に、実行中のインスタンスに ssh 接続して root になります:

.. code-block:: bash

   ssh -i theKey ubuntu@ip.of.running.instance

   sudo su

..
    5. Install the chef client and execute the chef-solo run:

5. Chef クライアントをインストールして chef-solo コマンドを実行します:

.. note::
   .. 
       When prompted for the Chef Server URL, just hit enter. 
       This tutorial does not rely on a chef-server.

   Chef サーバー URL を要求するメッセージが表示されたら Enter を入力してください。このチュートリアルでは Chef サーバーは必要ありません。

.. code-block:: bash

   echo "deb http://apt.opscode.com/ `lsb_release -cs`-0.10 main" | sudo tee /etc/apt/sources.list.d/opscode.list
   sudo mkdir -p /etc/apt/trusted.gpg.d
   gpg --keyserver keys.gnupg.net --recv-keys 83EF826A
   gpg --export packages@opscode.com | sudo tee /etc/apt/trusted.gpg.d/opscode-keyring.gpg > /dev/null
   sudo apt-get update
   sudo apt-get -y upgrade
   sudo apt-get -y install chef

   tar -zxf wordpress-demo-prep.tar.gz > /dev/null 2>&1
   chef-solo -j node.json -c solo.rb 

.. note::
   ..
      For reference, when running this on a m1.large VM in th us-west-2 (Oregon)
      region, the above script took 3 minutes and 9 seconds.

   参考までに us-west-2 (Oregon) リージョンの m1.large VM 上で実行すると、前述したスクリプトは3分9秒かかりました。

..
    During this step, some packages necessary for running a typical LAMP stack application
    will be installed, along with the latest enStratus agent. Depending on your connection and
    mirror speeds, this may take up to 5-7 minutes.

この手順では、最新の enStratus エージェントと一緒に、標準的な LAMP スタックアプリケーションを実行するのに必要なパッケージ群がインストールされます。接続速度やミラー速度によって、この作業は5-7分かかります。

..
    The purpose of this step is to prepare the image for running PHP and MySQL applications,
    not to install the application itself, that comes later durin the launch and orchestration
    steps of a deployment launch.

この手順の目的は、アプリケーションそのもののインストールではなく、PHP と MySQL アプリケーションを実行するイメージの準備をすることです。これは後でデプロイを始めるときの作業手順で使います。

..
    Once this step completes, initiate the build of the machine image from within the
    enStratus console.

この手順が完了したら、enStratus コンソール内からマシンイメージのビルドを開始します。

.. warning::
   ..
       If the image is not built using the server actions > Make Image menu option
       in the enStratus console, it will not be available for use in the deployment. This measure
       is in place to protect users from attempting to use an image that does not have the agent
       on it for automation.

   enStratus コンソールの "server actions > Make Image menu option" からイメージをビルドしない場合は、デプロイで使えません。その判断基準としては、自動化のためにその環境にエージェントを持たないイメージを使うのからユーザーを保護するために行います。

.. note::
   ..
       As a sanity check that the agent is working, you should see an expanded list of
       options in the actions menu as shown.

   エージェントが動作していることの健全性チェックとして、次のアクションメニューに選択肢のリストが展開されて見えるかを確認します。

..
   Server, Make Image

.. figure:: ./images/makeImage1.png
   :height: 700px
   :width: 2500 px
   :scale: 35 %
   :alt: Server, Make Image
   :align: center

   サーバー、イメージの作成

..
    Once this process completes, select action > Make Image from the server's action menu.

この処理が完了したら、サーバーアクションメニューから "action > Make Image" を選択してください。

..
   Make Image

.. figure:: ./images/makeImage0.png
   :height: 300px
   :width: 700 px
   :scale: 50 %
   :alt: Make Image
   :align: center

   イメージの作成

..
    While the image builds, it's time to upload the service images for use by enStratus.

イメージのビルド中に、enStratus が使うサービスイメージをアップロードすると良いです。
