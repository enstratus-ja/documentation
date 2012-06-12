..
    Access Rights
    -------------

.. _saas_access_rights:

アクセス権
----------

..
    **The real power of the enStratus user security approach is unlocked when working with
    Roles.**

**enStratus のユーザーセキュリティの取り組みが真の力を発揮するのは、ロールを使うときです。**

..
    Roles control user access to the enStratus console. Roles are assigned to Groups in a
    one-to-one relationship. Each role contains a customizable collection of access rights.
    Each access right provides access to a certain element of the enStratus console.

ロールは、enStratus コンソールへのユーザーアクセスを制御します。ロールは、1対1の関係をグループに割り当てられます。各ロールには、カスタマイズ可能なアクセス権のコレクションが含まれています。それぞれのアクセス権は、enStratus コンソールの特定要素へのアクセスを提供します。

..
    Terms
    ~~~~~

要項
~~~~

**RESOURCE:** 

..
    Every page, link and action in the enStratus console is controlled by at
    least one resource. In most cases, resources correspond to pages. For example, access to
    the actions available on the Machine Images page is controlled by the IMAGE resource and
    access to the actions available on the Servers page is controlled by the SERVER resource.
    Read access and account administration is controlled by the CONSOLE resource.

enStratus コンソールの全てのページ、リンク、アクションは、少なくとも1つのリソースにより制御されます。ほとんどの場合、リソースはページに対応しています。例えば、"Machine Images" ページで利用可能なアクションへのアクセスは IMAGE リソース、"Server" ページで使用可能なアクションへのアクセスは SERVER リソースにより制御されます。Read アクセスやアカウント管理は、CONSOLE リソースにより制御されます。

**ACTION:** 

..
    Resources are divided into actions. If you want access to all actions within a
    resource use the ANY action. If you want the role to have more granular permissions select
    the specific actions you want users to be able to perform. For example, if you want users
    with your role to be able to start deployments and services add the Deployment-Launch action.
    Some console actions require multiple resource-action pairs. These are documented in the
    Important Combinations sections for each resource.

リソースは、アクションに分かれています。リソースの全アクションにアクセスしたいなら "ANY" アクションを使います。より細かなアクセス許可のロールを望むなら、ユーザーが実行できるようにしたい特定のアクションを選択します。例えば、デプロイメントとサービスを開始できるロールを持ったユーザーが必要なら、"Deployment-Launch" アクションを追加します。複数のコンソールアクションは、複数のリソースとアクションの組み合わせを必要とします。この内容については、各リソースの "重要な組み合わせ" のセクションに記述されています。

**QUALIFIER:** 

..
    There are five different qualifiers: ANY, GROUP, THIS GROUP, BILLING, and
    MINE. These represent ownership of resources such as servers and machine images. For exam-
    ple, when a user launches a server they can associate it with a group and a billing code.
    The server that is launched is owned by the group and billing code assigned to it and the
    user who launched it. With access rights you can limit access to the server to users who
    belong to the group you chose, the chosen billing code, or the user who launched the
    server.

ANY, GROUP, THIS GROUP, BILLING, MINE の5つの異なる権限対象 (qualifier) があります。これらは、サーバーやマシンイメージなどのリソースの所有権を表します。例えば、ユーザーがサーバーを起動したとき、そのユーザーをグループや課金コードに関連付けできます。サーバーを起動したユーザーとそのサーバーに関連付けられたグループや課金コードが、サーバーを所有します。アクセス権を使うことで、ユーザーのサーバーへのアクセスを選択したグループに所属するユーザー、選択した課金コード、サーバーを起動したユーザーに制限できます。

..
    If you want users in your role to have access to all servers you can use the ANY
    qualifier. For some resources, such as console and firewall, the group, this group,
    billing, and mine qualifiers have no meaning because there is no ownership associated with
    the resource. In these cases you should always use ANY when adding access rights.

ロールをもつユーザーが全サーバーへアクセスしたいなら、権限対象に ANY を使います。コンソールやファイアウォールのようなリソースに関しては、GROUP, THIS GROUP, BILLING, MINE の権限対象は意味を為しません。というのは、リソースに関連付けられた所有権がないからです。この場合は、アクセス権を追加するときに常に ANY を設定する必要があります。

..
    Note: Ownership of some resources are still under development.

.. note::

   リソースの所有者は、まだ開発中です。

..
    Roles Example
    ~~~~~~~~~~~~~

ロールの例
~~~~~~~~~~

..
    You have three servers with the following ownership:

次の所有者をもつ3つのサーバーがあります。

..
    +----------+------------+--------------+---------------+
    | Resource | User Group | Budget Code  | Owner         |
    +==========+============+==============+===============+
    | Server 1 | QA         | Default      | Johnson, Erik |
    +----------+------------+--------------+---------------+
    | Server 2 | Dev        | Default      | Hoffman, Jeff |
    +----------+------------+--------------+---------------+
    | Server 3 | Dev        | Imaging      | Moselle, Greg |
    +----------+------------+--------------+---------------+

.. tabularcolumns:: |l|l|l|l|

+-----------+------------------+--------------+---------------+
| リソース  | ユーザーグループ | 予算コード   | 所有者        |
+===========+==================+==============+===============+
| サーバー1 | QA               | Default      | Johnson, Erik |
+-----------+------------------+--------------+---------------+
| サーバー2 | Dev              | Default      | Hoffman, Jeff |
+-----------+------------------+--------------+---------------+
| サーバー3 | Dev              | Imaging      | Moselle, Greg |
+-----------+------------------+--------------+---------------+

..
    *Objective* 

*対象*

..
    You are adding an access right to your QA Role, which is associated with your
    QA Group, using the resource SERVER and the action Image. This is what each qualifier will
    allow members of the QA group to do:

リソース SERVER とアクション Image を使う QA グループに関連付けられた QA リソースを追加しています。これは、それぞれの権限対象により QA グループのメンバーが実行できる内容を表します。

**ANY**

..
    QA users can image Server 1, Server 2, and Server 3.

QA ユーザーは、サーバー1、サーバー2、サーバー3 に対して Image アクションを実行できます。

**GROUP**

..
    QA users can image Server 1. They can image Server 2 and Server 3 if they are
    also members of the Dev group.

QA ユーザーは、サーバー1に対して Image アクションを実行できます。また Dev グループのメンバーであれば、そのユーザーはサーバー2とサーバー3に対して Image アクションを実行できます。

**THIS_GROUP**

..
    QA users can only image Server 1.

QA ユーザーは、サーバー1に対してのみ Image アクションを実行できます。

**BILLING**

..
    QA users can image Server 1 and Server 2 if they are associated with the
    Default billing code. They can image Server 3 if they are associated with the Imaging
    billing code.

QA ユーザーは、Default の課金コードに関連付けられているなら、サーバー1とサーバー2に対して Image アクションを実行できます。そのユーザーが Imaging の課金コードに関連付けられているなら、サーバー3に対して Image アクションを実行できます。

**MINE**

..
    Erik can image Server 1, Jeff can image Server 2, and Greg can image Server 3.

Erik はサーバー1に、Jeff はサーバー2に、Greg はサーバー3に対して、それぞれ Image アクションを実行できます。
