..
    Key Manager
    -----------

キーマネージャ
--------------

..
    Required Knowledge
    ~~~~~~~~~~~~~~~~~~

必要な情報
~~~~~~~~~~

..
    #. MySQL Root Password
    #. Java Home

#. MySQL ルートパスワード
#. Java ホーム

..
    Relevant files 
    ~~~~~~~~~~~~~~

関連ファイル
~~~~~~~~~~~~

..
    kmInstaller.tar.gz, when extracted, will generate a km/ directory containing:

kmInstaller.tar.gz を解凍すると、"km/" をディレクトリを作成して次のように展開されます:

#. files
#. installDB.sh 
#. installKM.sh

..
    Next, move the setup/ directory from the keygen directory, so that the contents of the km/ directory are, after this step:

次に "keygen" ディレクトリから、"km/" ディレクトリのコンテンツがある "setup/" ディレクトリへ移動します:

#. files/
#. installDB.sh 
#. installKM.sh
#. setup/

..
    Upon completion of this step, you will have installed the enStratus key management
    software component and the credentials database.  The setup/install.credentials file will
    be appended with the username and password used by the KM service to connect to its
    database along with a list of the configuration files used to configure the KM service.

この手順の完了時に、enStratus 鍵管理ソフトウェアコンポーネントと、データベースの認証情報をインストールします。setup/install.credentials ファイルには、鍵管理サービスの設定ファイルの一覧と一緒に、そのデーターベースへ接続するために鍵管理サービスが使うユーザー名とパスワードが追加されます。

..
    Key Manager Configuration Files
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

キーマネージャーの構成ファイル
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none

  [ KM Configuration Files ]

  /services/km/tomcat/webapps/ROOT/META-INF/context.xml
  /services/km/tomcat/conf/server.xml
