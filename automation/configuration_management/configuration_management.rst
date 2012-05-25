..
    Configuration Management
    ========================

構成管理
========

..
    This section provides information on using configuration management systems within the
    enStratus console.

このセクションでは、enStratus コンソール内で構成管理システムを使う方法を説明します。

..
    The enStratus console allows you to manage resources using two kinds of configuration
    management systems, Chef and Object Store.

enStratus コンソールでは、Chef と Object Store という2種類の構成管理システムを使ってリソースを管理できます。

Chef
----

..
    Chef is a configuration management tool created by Opscode. enStratus support both the
    hosted and private versions of Chef.

Chef は、Opscode が開発した構成管理ツールです。enStratus は、Chef のホストとプライベート両方のバージョンに対応しています。

..
    Object Store is a simple script based Configuration Management System that allows you to
    upload custom scripts into a cloud storage account, groups scripts into personalities, and
    automatically download and run the scripts when a new server is launched in your cloud
    account.
    Services

Object Store は、カスタムスクリプトをクラウドストレージアカウントや、グループスクリプトを関連場所にアップロードします。そして、クラウドで新たなサーバーが起動するとき、自動的にダウンロードして、そのスクリプトを実行します。

..
    To implement configuration management, you must first configure a service under
    Configuration Management > Services. If you choose Chef, you must supply an endpoint for
    the service. If you choose Object Store, you must choose a region and then a directory in
    which to store your scripts.

構成管理を設定するには、"Configuration Management > Services" からサービスを最初に設定しておく必要があります。Chef を選択するなら、そのサービスにエンドポイントを設定しなければいけません。Object Store を選択するなら、リージョンを選択してから、スクリプトを保存するディレクトリを指定しなければなりません。

..
    Accounts
    ~~~~~~~~

アカウント
~~~~~~~~~~

..
    Once your service has been configured, you will need to create an account associated with
    that service under Configuration Management > Accounts. When you set up an account for a
    Chef service you associate a set of credentials with that account. Credentials are not
    necessary for Object Store services.

サービスを設定したら、"Configuration Management > Accounts" からそのサービスに関連付けるアカウントを作成する必要があります。Chef サービスにアカウントを設定する場合、そのアカウントの一連の認証情報を関連付けます。Object Store サービスは認証情報を必要としません。

..
    Multiple accounts may be attached to the same Chef service with different sets of
    credentials, but an Object Store service can be associated with only one configuration
    management account at a time.

Chef サービスは、複数アカウントを異なる認証情報で関連付けできますが、Object Store サービスは、1つの構成管理アカウントに1つの認証情報のみしか関連付けられません。
