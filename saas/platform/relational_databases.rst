..
    Relational Databases
    --------------------

.. _saas_relational_database:

関係データベース
----------------

..
    enStratus supports cloud based relational database management services through enStratus
    Relational Databases (RDBMS). This service allows the end user to operate, scale and
    manage their relational databases in the cloud. Relational database instances give you the
    full capabilities and features you would normally find on a familiar RDBMS.

enStratus は、"Relational Databases" (RDBMS) ページで、クラウドベースの関係データベース管理サービスに対応しています。このサービスを使って、エンドユーザーは、クラウドの関係データベースの運用、スケール、管理を行います。関係データベースのインスタンスは、馴染みのある RDBMS における完全な機能を提供します。

..
    Overview
    ~~~~~~~~

概要
~~~~

..
    enStratus currently supports cloud based relational database management with Amazon
    Relational Database Service (Amazon RDS). With a relational database instance you get the
    functions of a traditional database, plus scalability and redundancy in the cloud.

現在、enStratus は、Amazon 関係データベースサービス（Amazon RDS）でクラウドベースの関係データベース管理に対応しています。関係データベースインスタンスを使うことで、従来のデータベースの機能に加え、クラウドのスケーラビリティと冗長性が得られます。

..
    Creating a Relational Database
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

関係データベースの作成
~~~~~~~~~~~~~~~~~~~~~~

..
    To create a new relational database in the enStratus console navigate to Platform >
    Relational Databases. Click on +add database in the right corner of the table.

enStratus コンソールで新規の関係データベースを作成するには、"Platform > Relational Databases" に移動して、"+add database" をクリックします。

..
    Screenshot 1.

スクリーンショット 1

..
    Under the configuration tab you will see the fields for creating a database.

設定タブにデータベースを作成するフィールドが表示されます。

..
    Screenshot 2.

スクリーンショット 2

..
    The **Name** field is for a custom name to associate with your database.

**Name** フィールドは、データベースに関連付ける任意の名称です。

..
    The **Description** field can be a custom description of your database.

**Description** フィールドは、データベースの任意の説明です。

..
    The **Label** field helps you organize your RDBMS instances by providing a unique color label.

**Label** フィールドは、独自のカラーラベルにより、RDBMS インスタンスを整理するのに役立ちます。

..
    The **Engine** field currently supports MySQL 5.1 relational databases. More options will be
    provided as they become available.

**Engine** フィールドは、現在 MySQL 5.1 の関係データベースに対応しています。今後より多くの選択肢が利用可能になります。

..
    The **Product** field displays the different sizes available for the RDBMS and should be
    chosen to fit your needs. Database operating costs are proportional to the size, measured
    in compute power, of the provisioned datbase. See Amazon RDS for more information and
    current pricing.

**Product** フィールドは、RDBMS で利用可能なサイズを表示するので、要求にあったものを選択します。データベースの運用コストは、プロビジョニングされたデータベースの、処理能力やサイズに比例します。さらに詳細や現在の価格については、Amazon RDS を参照してください。

..
    The **Port** number is restricted to ranges 1150 – 65535.

**Port** 番号は、1150 – 6553 の範囲に制限されています。

..
    For the **Zone** field it is highly recommended that you choose a zone that is in the same
    location as your primary application server.

**Zone** フィールドは、プライマリのアプリケーションサーバーと同じ場所のゾーンの選択を強くお奨めします。

..
    Another Zone option is high availability. In AWS this is know as a Multi-AZ deployment.
    The high availability option improves database durability and takes extra measures to
    ensure the RDBMS has minimal down time. This involves provisioning and maintaining a
    running backup of the primary instance in another zone. If there is planned maintenance,
    instance failure or availability zone failure in the primary zone the RDBMS will
    automatically failover to the backup instance.

別のゾーンのオプションに "High Availability" があります。AWS では、これをマルチ AZ デプロイメントと呼びます。"High Availability" オプションは、RDBMS に特別な措置を講じダウンタイムを最小限に抑えることを保証して、データベースの永続性を向上させます。これにより、別ゾーンでのプロビジョニングとプライマリインスタンスのバックアップ実行によるメンテナンスを行います。メンテナンスが予定されていたり、プライマリゾーン内のインスタンス障害または可用性ゾーン障害の場合、RDBMS はバックアップインスタンスに自動的にフェイルオーバーします。

..
    The size you specify in the Storage field must be in the 5GB to 1TB range.

**Storage** フィールドで指定するサイズは、5GB から 1TB の範囲でなければいけません。

..
    After the above fields have been completed proceed to the permissions tab.

上記のフィールドの記入が完了した後で "Permissions" タブに移ります。

..
    Screenshot 3

スクリーンショット 3

..
    The **Admin User** and **Admin Password** fields are required.

**管理者ユーザ** と **管理者パスワード** は必須項目です。

..
    **Billing Code** and **User Group** are the billing code and user group attributes that enStratus
    will use to track billing charges and access rights tied to the user management and
    billing code offerings of enStratus.

**Billing Code** と **User Group** は、enStratus が請求料金とアクセス権を追跡し、enStratus のユーザー管理と課金コードオファリングに関連付ける課金コードやユーザグループの属性です。

..
    Upon save the RDBMS is launched and could take up to 15 minutes to show up in the
    enStratus console.

RDMS の保存時に起動が行われて、enStratus コンソールに表示するには最大15分かかることがあります。

..
    **Connecting to a Relational Database**

**関係データベースに接続**

..
    First you need to allow connections between your local ip and the database you want to
    connect to.

最初に接続したいローカル IP アドレスとデータベース間の接続を許可する必要があります。

..
    On the Platform > Relational Databases page, select actions > network access for the
    database you want to use.

"Platform > Relational Databases" から "actions > network access" で使いたいデータベースにアクセスします。

..
    Screenshot 4

スクリーンショット 4

..
    If you have created a standard network (on the Company Settings > Standard Networks page)
    for the IP you want to connect to your database from you can select your standard network
    from the Source drop-down. If you have not created a standard network you can make a new
    one on the Company Settings > Standard Networks page or you can type your CIDR in the CIDR
    field and the Source will be labeled Custom. Click the Allow Access button and you will
    have network access to the database in 5 minutes or less.

("Company Settings > Standard Networks" から) 標準のネットワークを作成した場合、データベースに接続する IP はソースドロップダウンリストから選択できます。標準のネットワークをまだ作成していない場合、"Company Settings > Standard Networks" から新規のネットワークを作成するか、CIDR フィールドで IP アドレス/ネットマスクの CIDR 表記を入力できます。すると、"Source" に "Custome" ラベルが付きます。"Arrow Access" ボタンをクリックすると、5分以内にデータベースへアクセスできるようになります。

..
    Screenshot 5

スクリーンショット 5

..
    Next, view the info page for your database by selecting actions > info in the relational
    databases table.

次に、関係データベーステーブルで "actions > info" を選択して、データベースの情報ページを表示します。

..
    You can then connect to your database using a MySQL client, the Admin User, Admin Password
    and Port you specified in the Create RDBMS form, and the DNS/Host specified in the Info
    page.

次に、"Create RDBMS" フォームで指定した MySQL クライアント、管理者ユーザー、管理者パスワード、ポート、"Info" ページに指定した "DNS/Host" を使ってデータベースに接続できます。

..
    Other Actions
    ~~~~~~~~~~~~~

その他のアクション
~~~~~~~~~~~~~~~~~~

..
    To change the admin password for your relational database instance click on actions >
    change password in the Relational Databases table. You can't change the admin user name,
    but you can change the password by typing a new password in the Admin Password box and
    clicking the "Change RDBMS Password" button.

関係データベースインスタンスの管理者パスワードを変更するには、関係データベーステーブルの "actions > change password" をクリックします。管理者ユーザー名を変更することはできませんが、管理者パスワードに新しいパスワードを入力して "Change RDBMS Password" ボタンをクリックするとパスワードを変更できます。

..
    To terminate a relational database instance click on actions > terminate in the Relational
    Databases table.

関係データベースインスタンスを終了するには、関係データベーステーブルの "actions > terminate" をクリックします。
