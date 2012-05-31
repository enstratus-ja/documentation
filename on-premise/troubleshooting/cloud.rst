..
    Adding a Cloud to enStratus 
    ---------------------------

enStratus にクラウドを追加
--------------------------

..
    Process
    ~~~~~~~

作業手順
~~~~~~~~

..
    #. Backup the provisioning database
    #. Dump an entry from the cloud table
    #. Edit the cloud table entry
    #. Add new entry in the cloud table
    #. Stop the dispatcher service
    #. Start the dispatcher service
    #. Enter the cloud credentials

#. プロビジョニングされたデータベースのバックアップ
#. クラウドテーブルからエントリーのダンプ
#. クラウドテーブルのエントリーの編集
#. クラウドテーブルに新しいエントリーの追加
#. ディスパッチャーサービスの停止
#. ディスパッチャーサービスの開始
#. クラウドの認証情報の入力

..
    Backup the provisioning database
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

プロビジョニングされたデータベースのバックアップ
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..
    To backup the provisioning database issue the following command, replacing PASSWORD with
    the password of your provisioning database user. The password can be found in the
    install.credentials file from the installation.

プロビジョニングされたデーターベースをバックアップするには、次のコマンドを実行します。プロビジョニングされたデーターベースユーザーのパスワードを適切なものに置き換えて実行してください。パスワードは、インストールのセクションで紹介した install.credentials ファイルにあります。

.. code-block:: bash
	
	mysqldump -uprovisioning -p provisioning > provisioningBackup.sql

..
    Dump an entry from the cloud table
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

クラウドテーブルからエントリーのダンプ
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..
    In this step, we'll dump a single entry that will serve as the starting point for creating
    a private cloud endpoint. In this case, we'll dump the Amazon EC2 cloud entry, which is
    cloud_id=1.

この手順では、プライベートクラウドのエンドポイントを作成するための開始点を提供する1つのエントリーをダンプします。この例では、cloud_id=1 の Amazon EC2 のクラウドエントリーをダンプします。

.. code-block:: bash
	
	mysqldump -uprovisioning -p provisioning cloud --where="cloud_id=1" > amazonCloud.sql

..
    The line to edit from this file is here (cleaned up for clarity):

このファイルから編集するのは次の内容です (分かりやすく整形しています):

.. code-block:: mysql

	INSERT INTO `cloud` VALUES (
	1,
	'Y',
	'Amazon Web Services',
	'org.dasein.cloud.aws.AWSCloud',
	'Y',
	NULL,
	'https://ec2.sa-east-1.amazonaws.com',
	'Amazon',
	'AWS_ACCOUNT_NUMBER',
	'AWS_ACCESS_KEY',
	'AWS_SECRET_ACCESS_KEY',
	'AWS_CERTIFICATE',
	'AWS_PRIVATE_KEY',
	NULL,
	NULL,
	NULL,
	NULL,
	NULL,
	NULL,
	NULL,
	NULL,
	'/clouds/aws.gif',
	'http://status.aws.amazon.com/',
	'http://aws.amazon.com',
	'amazonaws.com');

..
    Let's say we're going to be connecting enStratus to a private OpenStack cloud, with the following properties:

次のプロパティ情報で enStratus から OpenStack のプライベートクラウドに接続してみましょう:

..
    #. Cloud API Endpoint: http://12.13.14.15:5000/v1
    #. Cloud Account/Tenant: DevOps
    #. Username: Rudy
    #. Password: Canoza

#. クラウド API エンドポイント: http://12.13.14.15:5000/v1
#. クラウドアカウント/テナント: DevOps
#. ユーザー名: Rudy
#. パスワード: Canoza

..
    The current values for the Cloud are:

このクラウドの現在の設定値です:

..
    +--------------------------+-------------------------------------+
    | Field                    | Amazon Value                        |
    +--------------------------+-------------------------------------+

.. tabularcolumns:: |l|l|

+--------------------------+-------------------------------------+
| 項目                     | Amazon 設定値                       |
+==========================+=====================================+
| cloud_id                 | 1                                   |
+--------------------------+-------------------------------------+
| available                | Y                                   |
+--------------------------+-------------------------------------+
| name                     | Amazon Web Services                 |
+--------------------------+-------------------------------------+
| delegate                 | org.dasein.cloud.aws.AWSCloud       |
+--------------------------+-------------------------------------+
| supports_addresses       | Y                                   |
+--------------------------+-------------------------------------+
| owner                    | NULL                                |
+--------------------------+-------------------------------------+
| endpoint                 | https://ec2.sa-east-1.amazonaws.com |
+--------------------------+-------------------------------------+
| provider_name            | Amazon                              |
+--------------------------+-------------------------------------+
| account_label            | AWS_ACCOUNT_NUMBER                  |
+--------------------------+-------------------------------------+
| api_id_label             | AWS_ACCESS_KEY                      |
+--------------------------+-------------------------------------+
| api_secret_label         | AWS_SECRET_ACCESS_KEY               |
+--------------------------+-------------------------------------+
| x509_cert_label          | AWS_CERTIFICATE                     |
+--------------------------+-------------------------------------+
| x509_key_label           | AWS_PRIVATE_KEY                     |
+--------------------------+-------------------------------------+
| storage_delegate         | NULL                                |
+--------------------------+-------------------------------------+
| storage_endpoint         | NULL                                |
+--------------------------+-------------------------------------+
| storage_account_label    | NULL                                |
+--------------------------+-------------------------------------+
| storage_api_id_label     | NULL                                |
+--------------------------+-------------------------------------+
| storage_api_secret_label | NULL                                |
+--------------------------+-------------------------------------+
| storage_x509_cert_label  | NULL                                |
+--------------------------+-------------------------------------+
| storage_x509_key_label   | NULL                                |
+--------------------------+-------------------------------------+
| key_info_text            | NULL                                |
+--------------------------+-------------------------------------+
| provider_logo_url        | /clouds/aws.gif                     |
+--------------------------+-------------------------------------+
| provider_status_url      | http://status.aws.amazon.com/       |
+--------------------------+-------------------------------------+
| provider_web_url         | http://aws.amazon.com               |
+--------------------------+-------------------------------------+
| cloud_identifier         | amazonaws.com                       |
+--------------------------+-------------------------------------+

..
    For the OpenStack cloud, we're going to change the parameters:

OpenStack クラウド向けに、このパラメーターを変更します:

..
    +--------------------------+--------------------------------------------------+------+
    | Field                    | OpenStack Value                                  | Note |
    +--------------------------+--------------------------------------------------+------+

.. tabularcolumns:: |l|l|c|

+--------------------------+--------------------------------------------------+------+
| 項目                     | OpenStack 設定値                                 | 備考 |
+==========================+==================================================+======+
| cloud_id                 | 1000                                             | 1    |
+--------------------------+--------------------------------------------------+------+
| available                | Y                                                |      |
+--------------------------+--------------------------------------------------+------+
| name                     | My Openstack Cloud                               | 2    |
+--------------------------+--------------------------------------------------+------+
| delegate                 | org.dasein.cloud.openstack.nova.os.NovaOpenStack | 3    |
+--------------------------+--------------------------------------------------+------+
| supports_addresses       | Y                                                |      |
+--------------------------+--------------------------------------------------+------+
| owner                    | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| endpoint                 | http://12.13.14.15:5000/v1                       |      |
+--------------------------+--------------------------------------------------+------+
| provider_name            | My Company                                       |      |
+--------------------------+--------------------------------------------------+------+
| account_label            | OpenStack_Tenant                                 | 4    |
+--------------------------+--------------------------------------------------+------+
| api_id_label             | USER_NAME                                        | 5    |
+--------------------------+--------------------------------------------------+------+
| api_secret_label         | PASSWORD                                         | 6    |
+--------------------------+--------------------------------------------------+------+
| x509_cert_label          | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| x509_key_label           | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| storage_delegate         | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| storage_endpoint         | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| storage_account_label    | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| storage_api_id_label     | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| storage_api_secret_label | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| storage_x509_cert_label  | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| storage_x509_key_label   | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| key_info_text            | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| provider_logo_url        | /clouds/openstack.png                            |      |
+--------------------------+--------------------------------------------------+------+
| provider_status_url      | NULL                                             |      |
+--------------------------+--------------------------------------------------+------+
| provider_web_url         | http://www.openstack.org                         |      |
+--------------------------+--------------------------------------------------+------+
| cloud_identifier         | openstack.org                                    |      |
+--------------------------+--------------------------------------------------+------+

..
    **Notes**

**備考**

..
    #. The cloud id must be a unique value in the cloud table.
    #. Simply a name for your cloud.
    #. The delegate is the identifier enStratus uses to interact with the cloud.
    #. This field will cause enStratus to present a field labeled 'Account' when entering cloud credentials.
    #. This field will cause enStratus to present a field labeled 'User Name' when entering cloud credentials.
    #. This field will cause enStratus to present a field labeled 'Password' when entering cloud credentials.

#. クラウド ID は、クラウドテーブルで一意な ID でなければいけません。
#. 単純にクラウドの名前です。
#. "delegate" は、enStratus がクラウドと対話的にやり取りするときに使う識別子です。
#. クラウドの認証情報を入力するときに enStratus が 'Account' というラベル名が付いた項目を表示します。
#. クラウドの認証情報を入力するときに enStratus が 'User Name' というラベル名が付いた項目を表示します。
#. クラウドの認証情報を入力するときに enStratus が 'Password' というラベル名が付いた項目を表示します。

.. note::
   ..
       Do **NOT** enter your credentials directly into the database. Enter them via the enStratus console.

   認証情報を直接データベースへ入力しては **いけません** 。enStratus コンソール経由で入力してください。

..
    With this information, we can now craft an insert statement for the cloud table:

この情報を使って、クラウドテーブルへの insert 文を作成します:

..
    Edit the cloud table entry
    ^^^^^^^^^^^^^^^^^^^^^^^^^^

クラウドテーブルのエントリーの編集
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: mysql

	INSERT INTO `cloud` VALUES (
	1000,
	'Y',
	'My Openstack Cloud', 
	'org.dasein.cloud.openstack.nova.os.NovaOpenStack',
	'Y',
	NULL                               						  
	'http://12.13.14.15:5000/v1',
	'My Company',                          						  
	'OpenStack_Tenant',
	'USER_NAME',
	'PASSWORD',
	NULL,
	NULL,
	NULL,
	NULL,
	NULL,
	NULL,
	NULL,
	NULL,
	NULL,
	NULL,
	'/clouds/openstack.png',
	NULL,
	'http://www.openstack.org',
	'openstack.org');

..
    Add new entry in the cloud table
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

クラウドテーブルに新しいエントリーの追加
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..
    Run the insert statement for the cloud table.

クラウドテーブルへの insert 文を実行します。

..
    Stop the dispatcher service
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^

ディスパッチャーサービスの停止
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: bash
  
  /etc/init.d/enstratus-dispatcher stop

..
    Start the dispatcher service
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^

ディスパッチャーサービスの開始
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: bash
  
  /etc/init.d/enstratus-dispatcher start

..
    Enter the cloud credentials
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^

クラウドの認証情報の入力
^^^^^^^^^^^^^^^^^^^^^^^^

..
    Create a new account and enter your cloud credentials. enStratus will validate the
    credentials set against your cloud endpoint and begin auto-discovering your
    infrastructure.

新しいアカウントを作成し、クラウドの認証情報を入力します。enStratus は、クラウドのエンドポイントに対してこの認証情報を検証して、そのインフラストラクチャーを自動検出し始めます。
