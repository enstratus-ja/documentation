IAM
---

..
    enStratus now supports the IAM feature for Amazon and Eucalyptus cloud environments.
    enStratus acts as a nexus through which authoritative user management is coordinated with
    the cloud provider. The integrated IAM feature in enStratus allows an administrator user
    of an account to securely control access to cloud console and api services and resources
    for users in that particular account. 

enStratus は、Amazon と Eucalyptus の IAM 機能に対応しています。enStratus は、ユーザー認証の管理をクラウドプロバイダーと連携するプラットフォームとして機能します。enStratus で統合される IAM 機能は、アカウントの管理者ユーザーにクラウドコンソール、API サービス、特定アカウントのユーザーのリソースに対してセキュアなアクセス制御を提供します。

..
    Providing Cloud Console Access for enStratus Users
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

enStratus ユーザーへ Cloud Console Access の提供
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    There are two ways an admin enStratus user can provide cloud console access to users.

enStratus の管理者ユーザーが、ユーザーに対するクラウドコンソールアクセスを提供する方法が2つあります。

..
    #. Cloud Console Access (Console Access using password)
    #. API Console Access  (API Access using API keys)

#. Cloud Console Access (パスワードを使ったコンソールアクセス)
#. API Console Access (API キーを使ったアクセス)

.. note::
   ..
       enStratus does not automatically generate Cloud Console Access and API Console
       Access when the user is created. In order to provide access, an admin user must manually
       grant access to the user from the user list page. 

   enStratus は、ユーザーが作成されたときに Cloud Console Access や API Console Access を自動的に生成しません。アクセスを提供するには、管理者ユーザーは、手動でユーザーリストページからユーザーへアクセス権を与える必要があります。

..
   Users, Users

.. figure:: ./images/image10.png
   :height: 150px
   :width: 700 px
   :scale: 95 %
   :alt: Users, Users
   :align: center

   ユーザー、ユーザー

..
    An admin user can edit a user’s cloud access settings in the User List table of the Users
    > Users page in the enStratus console.

管理者ユーザーは、enStratus コンソールで "Users > Users" ページのユーザーリストテーブルからユーザーのクラウドアクセス設定を編集できます。

..
   Users, Actions

.. figure:: ./images/image05.png
   :height: 250px
   :width: 400 px
   :scale: 95 %
   :alt: Users, Actions
   :align: center

   ユーザー、アクション

..
    The admin user can edit a user by clicking the ‘actions’ link in the User List table.
    Selecting the ‘Edit Cloud Access’ option from the drop down list will prompt the user with
    the following options:

管理者ユーザーは、ユーザーリストテーブルの "action" リンクをクリックしてユーザー情報を編集できます。ドロップダウンリストから "Edit Cloud Access" オプションを選択すると、次のオプションが表示されます。

..
   Users, Actions

.. figure:: ./images/image09.png
   :height: 250px
   :width: 400 px
   :scale: 95 %
   :alt: Users, Actions
   :align: center

   ユーザー、アクション

..
    Checking either one of the boxes for the first time and clicking the Save User button will
    add the user to the cloud provider’s IAM user list. Unchecking the boxes will revoke the
    user’s access to the cloud provider’s console. Please wait about 2-3 minutes between
    adding and revoking accesses. Modifying the same user’s cloud access rapidly can result in
    a delay synchronizing with the cloud provider.

最初にチェックボックスのどちらかを選択して、"Save User" ボタンをクリックすると、クラウドプロバイダーの IAM ユーザーリストにユーザーを追加します。チェックボックスからチェックを外すと、クラウドプロバイダーのコンソールへのアクセス権が無効になります。アクセス権の追加と取り消しには、約2-3分待ってください。同じユーザーのクラウドのアクセス権をどんどん変更すると、クラウドプロバイダーとの同期のために遅延します。

..
    When only Cloud Console Access is checked and the user is saved, enStratus will generate a
    login password which can be used by that user to login to the cloud provider (e.g. AWS)
    console. 

Cloud Console Access のみ選択してユーザーを保存すると、enStratus はクラウドプロバイダーコンソール (例 AWS) へログインするためのパスワードを生成します。

..
   Cloud Console, Access

.. figure:: ./images/image06.png
   :height: 300px
   :width: 400 px
   :scale: 95 %
   :alt: Cloud Console, Access
   :align: center

   クラウドコンソール、アクセス

..
    An enStratus user who has been granted Cloud Console Access can check their Cloud Console
    Password under the ‘Edit My Profile’ page.

Cloud Console Access を与えた enStratus ユーザーは、"Edit My Profile" ページで Cloud Console Password を確認できます。

..
   Cloud Access, Check Password

.. figure:: ./images/image02.png
   :height: 150px
   :width: 400 px
   :scale: 95 %
   :alt: Cloud Access, Check Password
   :align: center

   クラウドアクセス、パスワード確認

..
    The user will have the option to show or hide the console password.

ユーザーは、コンソールパスワードの表示/非表示を切り替えるオプションを選べます。

..
   Cloud Access, Show Password

.. figure:: ./images/image07.png
   :height: 100px
   :width: 400 px
   :scale: 95 %
   :alt: Cloud Access, Show Password
   :align: center

   クラウドアクセス、パスワード表示

..
    For example, if the enStratus user’s cloud provider is Amazon and the user wants to verify
    the password, the user should be provided with an account specific link for the login page
    by the admin user. 

例えば、enStratus ユーザーのクラウドプロバイダーが Amazon であり、そのユーザーがパスワードを確認したいなら、管理者ユーザーによりログインページにアカウント設定リンクを表示するようにします。

..
    For AWS see: http://aws.amazon.com/iam/faqs/#How_do_i_know_what_the_link_is

AWS はこちらを参照してください: http://aws.amazon.com/iam/faqs/#How_do_i_know_what_the_link_is

..
    Then the enStratus user will have to provide the proper username,  which is the User ID
    from the User List table in the enStratus console, and the Cloud Console Password, which
    is displayed in the ‘Edit My Profile’ page of the enStratus Console. 

enStratus ユーザーは、enStratus コンソールのユーザーリストテーブルの User ID である適切なユーザー名と、enStratus コンソールの "Edit My Profile" ページに表示される Cloud Console Password を提供する必要があります。

..
    Similarly when only the API Console Access is checked and the user is saved, enStratus
    will generate API keys with the underlying cloud provider. 

同様に、API Console Access のみを選択してユーザーを保存すると、enStratus はクラウドプロバイダーで使う API キーを生成します。

..
   API Access

.. figure:: ./images/image01.png
   :height: 300px
   :width: 400 px
   :scale: 95 %
   :alt: API Access
   :align: center

   API アクセス

..
    An enStratus user who has been granted API Console Access can now find their API access
    keys under ‘Edit My Profile’ page.

ここで API Console Access を与えた enStratus ユーザーは、"Edit My Profile" ページで API キーを見つけられます。

..
   View API Keys

.. figure:: ./images/image00.png
   :height: 150px
   :width: 400 px
   :scale: 95 %
   :alt: View API Keys
   :align: center

   API キーの表示

..
    The enStratus user can use these keys to make API calls to the cloud provider.

enStratus ユーザーは、クラウドプロバイダーへの API 呼び出しを行うためにこのキーを使います。

..
    If both of the boxes in the Edit Cloud Access form are checked, then the user is provided
    with both Cloud API keys and a Cloud Console password, and they are both displayed under
    the ‘Edit My Profile’ page. If both the boxes are unchecked while editing a user’s cloud
    access then both kinds of access are revoked and credentials are removed from the ‘Edit My
    Profile’ page.

"Edit Cloud Access" フォームで両方のチェックボックスを選択すると、そのユーザーは Cloud API キーと Cloud Console パスワードの両方を提供します。"Edit My Profile" ページでその両方が表示されます。ユーザーのクラウドアクセスを編集しているときに両方のチェックボックスを取り消すと、両方のアクセス権を無効にして、"Edit My Profile" ページから認証情報が削除されます。

.. note::
   ..
       Generating a cloud console access password or API access keys for an enStratus user
       for the first time creates an IAM user with the enStratus User Id as their username in the
       cloud provider’s console but does not attach a user policy to the user. The user will not
       have any set of permissions associated with it which prevents the user from performing any
       actions in the cloud provider’s console. 

   最初に enStratus ユーザーのために Cloud API キーや Cloud Console パスワードを生成することで、enStratus User ID をクラウドプロバイダーのコンソールのユーザー名として IAM ユーザーを作成します。但し、このユーザーはユーザーポリシーを設定しません。このユーザーには、クラウドプロバイダーのコンソールで任意のアクションを実行できないようにするユーザーポリシーに関連付けられた権限が何も設定されません。

..
    In order to provide an IAM user with proper access rights, the admin enStratus user must
    log into the cloud provider’s console and manually attach the proper user policy to the
    IAM user.  

適切なアクセス権を設定した IAM のユーザーを提供するには、enStratus の管理者ユーザーがクラウドプロバイダーのコンソールにログインして、この IAM ユーザーに適切なユーザーポリシーを手動で設定する必要があります。

..
    For example, for an IAM user in an Amazon cloud account:

例えば、Amazon クラウドアカウントの IAM ユーザーです:

..
    The admin user will log on to AWS console and select the IAM tab to display the list of IAM users.

管理者ユーザーが AWS コンソールにログインし、IAM のユーザー一覧を表示するために IAM タブを選択します。

..
   IAM Users, List

.. figure:: ./images/image04.png
   :height: 250px
   :width: 600 px
   :scale: 95 %
   :alt: IAM Users, List
   :align: center

   IAM ユーザー、リスト

..
    After the admin selects a user, a window below the IAM user list is displayed that allows
    for modifying the user’s attributes. Selecting the Permissions tab from that window will
    show the option to attach a user policy to a particular user. 

管理者がユーザーを選択した後で、IAM のユーザーリストの下部にユーザー属性を変更できる画面が表示されます。その画面から Permissions タブを選択して、特定ユーザーにユーザーポリシーを設定するオプションを表示します。

..
   IAM Policy, Single User

.. figure:: ./images/image08.png
   :height: 250px
   :width: 800 px
   :scale: 95 %
   :alt: IAM Policy, Single User
   :align: center

   IAM ポリシー、シングルユーザー

..
    A user can then be attached to different types of access rights based on the configuration
    selected by an administrator.

ユーザーは、管理者が選択した設定内容に基づく別の種類のアクセス権を設定できます。

..
   Access Rights, Edit

.. figure:: ./images/image03.png
   :height: 300px
   :width: 400 px
   :scale: 95 %
   :alt: Access Rights, Edit
   :align: center

   アクセス権、編集

..
    After the user has been attached to an appropriate user policy, the user will be able to
    log in to the AWS console and perform permissible actions and/or make permissible API
    calls.

ユーザーに適切なユーザーポリシーを設定した後で、このユーザーは AWS コンソールにログインして、許可されたアクションや API 呼び出しを実行できます。
