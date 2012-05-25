..
    Anatomy
    -------

構造
----

..
    The anatomy of a service is very free-form. This allows for great flexibility in designing
    or adapting an application for use in a multi-cloud environment.

サービスのディレクトリ構造は、かなり自由な形式です。これはマルチクラウド環境でより柔軟な設計を行う、またはアプリケーションを導入できるようにします。

..
    An enStratus service should have the following structure:

enStratus サービスは、次のようなディレクトリ構造にしておく必要があります。

bin
~~~

..
    Inside the bin/ directory, minimally 3 files:

bin ディレクトリには、最低限3つのファイルがあります:

#. enstratus-start
#. enstratus-stop
#. enstratus-configure

..
    The bin/ directory provides a known path for leveraging the enstratus orchestration and
    automation sections. When a service is deployed enStratus will, using the enStratus agent,
    trigger events to configure each service in the appropriate order.

bin ディレクトリは、enStratus と自動化のセクションを活用するためにあらかじめパスを提供します。サービスがデプロイされると、enStratus エージェントを使い、各サービスが適切な順序で設定されるように enStratus はイベントをトリガーします。

cfg
~~~

..
    The cfg directory is a directory where enStratus writes configuration files generated at
    run time with information the application will need to operate in the cloud. This
    directory is a good place for putting configuration file "templates".

cfg ディレクトリは、enStratus が実行時に生成した設定ファイルに書き込むディレクトリです。この設定ファイルには、アプリケーションがクラウド上で動作するために必要な情報が書き込まれます。このディレクトリは、"templates" という設定設定ファイルを置くのにも適切な場所です。

.. note::
   ..
       The astute chef user/reader will recognize the word template as a very useful
       construct from the Chef/Opscode world and that's precisely correct. As deployers of
       cloud applications, we use this cfg directory to stage files that will be written
       dynamically with ephemeral cloud information.

   明晰な Chef ユーザーは、Chef/Opscode の世界における便利な仕掛けとして template という単語を思い浮かべるでしょう。まさにその通りです。クラウドアプリケーションのデプロイヤーとして、一時的なクラウド情報を動的に書き込み、そのファイルを展開するために cfg ディレクトリを使います。

..
    And...that's it. Questions? :)

そして、、、これで以上です。質問は？ :)

..
    The bin/ and the cfg/ directories are the two primary directories used by the enStratus
    management system. Beyond that, additional directories can be added to suit the
    application. For example, a third directory might be:

bin と cfg ディレクトリは、enStratus 管理システムの2つの主要なディレクトリです。これらに加えて、アプリケーションによりディレクトリを追加できます。例えば、3番目のディレクトリは次のようになります:

app
~~~

index.html

..
    Where the application directory holds the application files, in this case a lonely
    index.html.

アプリケーションディレクトリは、アプリケーションファイルを置きます。今回は index.html のみです。

..
    MySQL Service
    ~~~~~~~~~~~~~

MySQL サービス
~~~~~~~~~~~~~~

..
    The MySQL service structure looks like this:

MySQL サービス構造は次のようになります:

bin/

.. hlist::
   :columns: 3

   * addDataSource
   * enstratus-backupDataSource
   * enstratus-configureDataSource
   * enstratus-lock
   * mysql
   * mysqlStartReplication
   * configureDataSource
   * enstratus-check
   * enstratus-dbgrant
   * enstratus-start
   * mysqlDump
   * configureMySQL                
   * enstratus-configure
   * enstratus-installds
   * enstratus-stop                
   * mysqlGrant

cfg/

.. hlist::
   :columns: 1
  
   * master.cnf
   * replicant.cnf 

data/

.. hlist::
   :columns: 1
    
   * ``<empty>``

log/

.. hlist::
   :columns: 1
    
   * ``<empty>``
