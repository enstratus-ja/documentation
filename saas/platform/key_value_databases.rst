..
    Key Value Databases
    -------------------

.. _saas_key_value:

キー/バリューデータベース
-------------------------

..
    enStratus Key/Value Databases (KV Databases or KVDB) are a simple solution for storing
    your data for high availability and scalability. With a KV database you get only what you
    need. You can simply query your data and return the results without having to manage
    different schemas for your stored data sets. You do not need to worry when storing new
    data because it is automatically indexed for you.

enStratus のキー/バリューデータベース (KV データベースまたは KVDB) は高可用性とスケーラビリティを備えたデータ格納の簡単なソリューションです。KV データベースを使うと、必要なものだけ得られます。単純にデータをクエリして、その他のスキーマを管理せずに格納されているデータセットを取得できます。新規のデータを保存するときに自動的にインデックスが作成されるため、そういったことを心配する必要はありません。

..
    Overview
    ~~~~~~~~

概要
~~~~

..
    enStratus currently supports the creation and termination of Amazon SimpleDB domains. See
    Amazon SimpleDB for more information and current pricing.

現在、enStratus は、Amazon SimpleDB domains の作成と終了に対応しています。さらに詳細や現在の価格については、Amazon SimpleDB を参照してください。

..
    KV databases are large collections of data organized into separate domains. The data is
    stored in hash tables that contain key to value pairs. The key to value pairs are
    attributes that can be searched in lexicographical queries.

KV データベースは、独立した領域で構成された巨大データのコレクションです。データは、キーとバリューのペアを含むハッシュテーブルに格納されています。キー/バリューのペアは、辞書式クエリ (lexicographical queries) で検索可能な属性です。

..
    Creating a Key/Value Database
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

キー/バリューデータベースの作成
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    To launch a new KV database in the enStratus console click on Platform > Key/Value
    Databases. Then click  +add key/value database.

enStratus コンソールで新規の KV データベースを起動するには、"Platform > Key/Value Databases" から "+add key/value database" をクリックします。

..
    Screenshot 1

スクリーンショット 1

..
    In the Create Key/Value Database form you will see the different fields for creating the
    KVDB.

"Add Key/Value Database" フォームでは、KVDB を作成するフィールドが表示されます。

..
    Screenshot 2

スクリーンショット 2

..
    The **Name** field is for a custom name to associate with your database.

**Name** フィールドは、データベースに関連付ける任意の名称です。

..
    The **Description** field can be a custom description for your database.

**Description** フィールドは、データベースの任意の説明です。

..
    The **Label** field helps you organize your KVDB instances by providing a unique color label.

**Label** フィールドは、独自のカラーラベルにより、KVDB インスタンスを整理するのに役立ちます。

..
    **Billing Code** and **User Group** are the billing code and user group attributes that enStratus
    will use to track billing charges and access rights tied to the user management and
    billing code offerings of enStratus.

**Billing Code** と **User Group** は、enStratus が請求料金とアクセス権を追跡し、enStratus のユーザー管理と課金コードオファリングに関連付ける課金コードやユーザグループの属性です。

..
    Upon save the KV database is launched. It can take up to 15 minutes to appear in the
    enStratus console.

KV データベースの保存時に起動が行われて、enStratus コンソールに表示するには最大15分かかることがあります。

..
    Terminating Key/Value Databases
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

キー/バリューデータベースの終了
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    To terminate a KVDB click actions > terminate in the Key/Value Databases table.

KVDB を終了するには、キー/バリューデータベーステーブルの "actions > terminate" をクリックします。

..
    Screenshot 3.

スクリーンショット 3
