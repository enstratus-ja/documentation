..
    Cloud Files
    -----------

.. _saas_cloudfiles:

クラウドファイル
----------------

..
    enStratus supports cloud file storage via the enStratus console. File storage allows users
    to store and retrieve important data for easy and reliable access.

enStratus は、コンソール経由でクラウドファイルストレージに対応しています。ファイルストレージでは、簡単且つ信頼性の高いアクセスにより、重要なデータの格納や取得ができます。

..
    enStratus supports cloud file storage in Amazon Simple Storage Service (Amazon S3),
    Windows Azure Storage Services, Google Storage, Eucalyptus Walrus, AT&T Synaptic Storage,
    OpenStack Object Storage (Swift), and Rackspace Cloud Files.

enStratus は、Amazon Simple Storage Service (Amazon S3), Windows Azure Storage Services, Google Storage, Eucalyptus Walrus, AT＆T Synaptic Storage, OpenStack Object Storage (Swift), Rackspace Cloud Files といったクラウドファイルストレージに対応しています。

..
    To create a new bucket through the enStratus console click on Platform > Files, then click
    on +create root-level directory.

新規バケットを作成するには、enStratus コンソールの "Platform > Files" から "+create root-level directory" をクリックしてディレクトリを作成します。

..
    Screenshot

スクリーンショット

.. note::
   ..
       you can create multiple root-level directories

   複数のルートレベルディレクトリを作成できます

..
    The **Name** field is for a custom name to associate with your directory.

**Name** フィールドは、ディレクトリに関連付ける任意の名称です。

..
    The **Label** field helps you organize your directories by providing a unique color label.

**Label** フィールドは、独自のカラーラベルにより、ディレクトリを整理するのに役立ちます。

..
    **Billing Code** and **User Group** are the billing code and user group attributes that enStratus
    will use to track billing charges and access rights tied to the user management and
    billing code offerings of enStratus.

**Billing Code** と **User Group** は、enStratus が請求料金とアクセス権を追跡し、enStratus のユーザー管理と課金コードオファリングに関連付ける課金コードやユーザグループの属性です。

..
    Once the directory is created you can create a hierarchy of directories within the
    root-level directory. Clicking on the actions tab next to the root-level directory will
    bring up options for that directory. These options include:

ディレクトリが作成されると、そのルートレベルディレクトリ内にディレクトリ階層を作成できます。ルートレベルディレクトリの横にある "actions" タブをクリックすると、そのディレクトリのオプションを表示します。これらのオプションは次の通りです。

..
    **Info**: Will provide information relating to the directory (e.g. directory name, user group,
    date created, parent directory, etc.)

**Info**: ディレクトリに関連する情報を提供します (例えば、ディレクトリ名、ユーザーグループ、作成日、親ディレクトリなど) 。

..
    Screenshot

スクリーンショット

..
    **Permissions**: You can set access level permissions to each directory.

**Permissions**: 各ディレクトリへのアクセスレベルの権限を設定できます。

..
    **Upload Files**: You can upload files to the given directory from your local machine.

**Upload Files**: ローカルマシンから指定されたディレクトリにファイルをアップロードできます。

..
    **New Directory**: Will create a new directory within the current working directory.

**New Directory**: 現在の作業ディレクトリに新規ディレクトリを作成します。

..
    **Delete**: Will remove the directory and it’s contents.

**Delete**: ディレクトリとその内容を削除します。

..
    After a file is uploaded, an action tab is placed next to the file and allows for you to
    manage the file. These options include:

ファイルのアップロード後、"action" タブがファイルの横に表示され、ファイル管理が行えます。これらのオプションは次の通りです:

..
    Info: Provides information about the file (e.g. creation date, last updated date, file
    size, etc.)

Info: ファイルについての情報を提供します (例えば、作成日、最終更新日付、ファイルサイズなど) 。

..
    Download: Will allow you to download the selected file to your local machine.

Download: ローカルマシンに選択したファイルをダウンロードできます。

..
    Note: This can take some time depending on file size and currently no progress bar has
    been implemented.

ファイルサイズによってはダウンロードに時間を要する可能性があるのに注意してください。また、現在はプログレスバーが実装されていません。

..
    Rename: Gives you the option to rename the file.

Rename: ファイル名を変更するオプションを提供します。

..
    Delete: Permanently removes the file from the directory.

Delete: ディレクトリからファイルを完全削除します。
