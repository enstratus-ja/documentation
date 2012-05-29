..
    Console
    -------

コンソール
----------

..
    Required Knowledge
    ~~~~~~~~~~~~~~~~~~

必要な情報
~~~~~~~~~~

..
    #. None :)

#. なし :)

..
    Relevant files 
    ~~~~~~~~~~~~~~

関連ファイル
~~~~~~~~~~~~

..
    consoleInstaller.tar.gz and the setup directory used during the
    installation of the enStratus Monitor and Worker services.

consoleInstaller.tar.gz と、enStratus モニターとワーカーサービスのインストール中に使った "setup" ディレクトリです。

..
    Extract the consoleInstaller.tar.gz file. There will be a console/ directory containing
    the following items:

consoleInstaller.tar.gz ファイルを展開してください。"console/" ディレクトリに次のように展開されます:

#. files
#. installDB.sh
#. installConsole.sh

..
    Next, move the setup/ directory from the monitorWorker/ directory, so that the contents of the
    console/ directory are, after this step:

次に "monitorWorker/" ディレクトリから、"console/" ディレクトリのコンテンツがある "setup/" ディレクトリへ移動します:

..
    Follow the prompts to complete the installation of the console service.

コンソールサービスのインストールを完了するために画面の指示に従ってください。

#. files/
#. installDB.sh
#. installConsole.sh
#. setup/

..
    Upon completion of this step, you will have installed and configured the enStratus console
    service along with the console and enstratus console datbases.

この手順の完了時に、enStratus のコンソールとそのコンソールデータベースと一緒にコンソールサービスのインストールと設定が行われます。

..
    The setup/install.credentials file will be appended with the username and password used by
    the console service to connect to its database along with a list of the configuration
    files used to configure the console service.

setup/install.credentials ファイルには、コンソールサービスの設定ファイルの一覧と一緒に、そのデーターベースへ接続するためにコンソールサービスが使うユーザー名とパスワードが追加されます。

..
    Console Configuration Files
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~

コンソール構成ファイル
~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none

  [ Console Configuration Files ]

  /services/console/bin/tomcat
  /services/console/bin/enstratus
  /services/console/tomcat/webapps/ROOT/META-INF/context.xml
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-webservices.cfg
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/dasein-persistence.properties
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-console.cfg
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/custom/networks.cfg
