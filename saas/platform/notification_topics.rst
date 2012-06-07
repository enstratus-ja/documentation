..
    Notification Topics
    -------------------

.. _saas_notification_topics:

通知トピック
------------

..
    enStratus supports management of cloud based notification topic web services through the
    enStratus console. Notification topics are often applied to an application and can be used
    to automatically send messages to subscribers or other applications.

enStratus は、コンソール経由でクラウドベースの通知トピック Web サービスの管理に対応しています。通知トピックは、普通はアプリケーションに適用され、購読者や別のアプリケーションへメッセージを自動送信するのに使えます。

..
    Overview
    ~~~~~~~~

概要
~~~~

..
    enStratus currently supports the creation and management of Amazon Simple Notification
    Service (Amazon SNS). See Amazon SNS for more information and current pricing.

現在、enStratus は、Amazon Simple Notification Service (Amazon SNS) の作成と管理に対応しています。さらに詳細や現在の価格については、Amazon SNS を参照してください。

..
    Notification topics makes it easy for the developer to send out important messages to
    applications or users. This allows for the developer to effectively communicate
    time-sensitive information in the form of a message.

通知トピックは、開発者が重要なメッセージをアプリケーションやユーザーへ簡単に送信できるようにします。これにより開発者が効率的に時間感度の高い情報をメッセージ形式で送信できます。

..
    Creating Notification Topics:

通知トピックの作成:

..
    Screenshot

..
    To create a new Notification Topic click on Platform > Notification Topics, then click on
    + add Topic.

新規の通知トピックを作成するには、"Platform > Notification Topics" から "+ add Topic" をクリックします。

..
    Screenshot

スクリーンショット

..
    The **Name** field is for a custom name to associate with your topic.

**Name** フィールドは、トピックの任意の名称です。

..
    The **Description** field can be a custom description for your topic.

**Description** フィールドは、トピックの任意の説明です。

..
    The **Label** field helps you organize your topics by providing a unique color label.

**Label** フィールドは、独自のカラーラベルにより、トピックを整理するのに役立ちます。

..
    **Billing Code** and **User Group** are the billing code and user group attributes that enStratus
    will use to track billing charges and access rights tied to the user management and
    billing code offerings of enStratus.

**Billing Code** と **User Group** は、enStratus が請求料金とアクセス権を追跡し、enStratus のユーザー管理と課金コードオファリングに関連付ける課金コードやユーザグループの属性です。

..
    Upon save your topic will be created and will appear shortly.

トピックの保存時に作成を行い、すぐに表示されます。

..
    Subscribing To Notification Topics
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

通知トピックの購読
~~~~~~~~~~~~~~~~~~

..
    Screenshot

..
    After the topic has been created you can add subscribers to the topic by clicking on
    actions > subscriptions.

トピックの作成後に、"actions > subscriptions" をクリックしてそのトピックに購読者を追加できます。

..
    Screenshot

スクリーンショット

..
    **End point** is where you can enter the end point as an email address, web services URL, or
    the Amazon Resource Name string on a SQS (Simple Queue Service) queue.

**End point** は、電子メールアドレス、Web サービスの URL、SQS (Simple Queue Service) キューの Amazon Resource Name string などをエンドポイントとして入力できます。

..
    **Data Format** is currently supported in JSON and plain text formats.

**Data Format** は、現在 JSON とプレーンテキスト形式に対応しています。

..
    Clicking Subscribe to Topic will add the subscriber.

"Subscribe to Topic" をクリックして購読者を追加します。

..
    Publishing To Notification Topics
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

通知トピックの送信
~~~~~~~~~~~~~~~~~~

..
    To publish a message to your subscribers click on actions > publish.

購読者へメッセージを送信するには、アクションで "actions > publish" をクリックします。

..
    Screenshot

スクリーンショット

..
    The Subject field can be any custom subject for your message.

**Subject** フィールドは、任意のメッセージ件名です。

..
    The Message field will be where you provide your custom message.

**Message** フィールドは、送信する任意のメッセージです。

..
    Deleting Notification Topics
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~

通知トピックの削除
~~~~~~~~~~~~~~~~~~

..
    To delete a notification topic click actions > delete in the Notification Topics table.

通知トピックを削除するには、通知トピックテーブルで "actions > delete" をクリックします。
