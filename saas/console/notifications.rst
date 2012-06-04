..
    Notifications
    -------------

.. _console_notifications:

通知機能
--------

..
    enStratus has expanded management of notifications and alerts, allowing for more granular control over events which will trigger a notification, as well as the mechanisms by which the notifications will be delivered. 

enStratus は、通知を配信する仕組みと同様に、通知をトリガーするイベントを使って細かく制御できる通知機能やアラートといった拡張管理機能をもっています。

..
    Account administrators will now be able to set separate preferences for each account, and individual users will also be able to control how they receive alerts and notifications.

アカウント管理者は、各アカウントを別々に設定できます。また、個々のユーザーもアラートや通知を受け取る方法を制御できます。

..
    Setting Notification Targets for Accounts and Users
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

アカウントやユーザーの通知対象の設定
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    Notification targets are endpoints to which notifications and alerts can be sent. You can specify the following endpoints:

通知対象は、通知とアラートが送られるエンドポイントです。次のエンドポイントを指定できます:

..
    * Email
    * SMS
    * API
    * Notification Topic

* 電子メール
* SMS
* API
* 通知トピック

..
   Alerts and Notifications targets

.. figure:: ./images/notifications_1.png
   :alt: Alerts and Notifications targets
   :align: center

   アラートと通知対象

..
    With Email and SMS notification targets specify an email address or mobile number (including country code) to send notifications. The API target allows you to specify an API endpoint for notifications. 

E メールと SMS の通知対象は、この通知を送る携帯電話番号 (国コードを含む)  やメールアドレスを指定します。API の対象は、通知のための API エンドポイントを指定できます。

..
    The Notification Topic Target allows you to leverage notification services such as Amazon SNS (`<http://aws.amazon.com/sns/>`_). Topics can be set up and configured at Platform > Notification Topics.

通知トピックの対象は、Amazon SMS (`<http://aws.amazon.com/sns/>`_) のような通知サービスを活用できます。このトピックは、"Platform > Notification Topics" から設定できます。

..
    Account administrators may set targets for notifications **specific to that account** at Account Settings > Account Notifications.

アカウント管理者は、通知のターゲットを "Account Settings > Account Notifications" で **そのアカウント特有** の設定が行えます。

..
    Users may set personal targets for notifications **across all their accounts** by editing their profile in their header menu.

ユーザーは、ヘッダーメニューのプロフィールを編集することにより、 **全てのアカウントを横断して** 通知の個人設定も行えます。

..
   Setting notification targets

.. figure:: ./images/notifications_2.png
   :alt: Setting Notification targets
   :align: center

   通知対象の設定

..
    Setting Account Alert and Notification Preferences
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

アカウントのアラートと通知の設定
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    Account administrators may set alert and notification preferences (as well as notification targets) by going to Account Settings > Account Notifications.

アカウント管理者は、"Account Settings > Account Notifications" に移動して (通知対象と同様に) 通知設定やアラートを設定できます。

..
    **Alert Preferences**

**アラート設定**

..
    Alerts are triggered by any alarm event such as unexpected server termination, backup failure, or intrusion detection.

アラートは、予期せぬサーバーの終了、バックアップの失敗、侵入検知などといった任意のアラートイベントをトリガーします。

..
    You can choose the minimum severity of the alerts you receive, and how you want to receive them.

アラートの最小重要度を選択して、受け取りたいアラートを選択できます。

..
   Alert Preferences

.. figure:: ./images/notifications_3.png
   :alt: Alert Preferences
   :align: center

   アラート設定

..
    **Notification Preferences**

**通知設定**

..
    enStratus allows granular control when it comes to notifications triggered by state change events. You choose a resource type (Any Resource, Server, Firewall, IP Address), a state change type (Create, Update, Delete), and the delivery targets.

enStratus は、状態変更イベントによりトリガーされた通知の配信を細かく制御できます。リソースの種類 (任意のリソース、サーバー、ファイアウォール、IP アドレス) を選択し、状態変更の種類 (作成、更新、削除) と配信先を選択します。

..
   Notification Preferences

.. figure:: ./images/notifications_4.png
   :alt: Notification Preferences
   :align: center

   通知設定

..
    If you choose identical delivery targets for Create, Update, and Delete on the same resource, those preferences will be consolidated. Otherwise notification settings are additive.

同じリソース上で作成、更新、削除に同一の配信対象を選択すると、それらの設定は統合されます。それ以外の通知設定は、任意の設定です。

..
    Consider the following preferences:

次の設定を見てみましょう:

.. figure:: ./images/notifications_5.png
   :alt: Notification Preferences
   :align: center

..
    In this example, a create event on any resource (ANY.CREATE) will trigger a notification to the Topic target. This includes Servers, Firewalls, and IP Addresses.
    An update event on a firewall (FIREWALL.UPDATE) will trigger an SMS notification.
    Any kind of event on a server (SERVER.ANY) will trigger both Email and Topic notifications.
    Updating or deleting an IP address will trigger NO notifications.
    Deleting a firewall will also trigger no notifications.

この例では、任意のリソース上の作成イベント (ANY.CREATE) は、通知をトピック対象にトリガーします。これはサーバー、ファイアウォール、IP アドレスを含みます。ファイアウォール上の更新イベント (FIREWALL.UPDATE) は、SMS 通知をトリガーします。サーバー上の任意のイベント (SERVER.ANY) は、E メールとトピック通知の両方をトリガーします。IP アドレスの更新や削除は、通知をトリガーしません。ファイアウォールの削除も同様に通知をトリガーしません。

..
    **Setting User Alert and Notification Preferences**

**ユーザーのアラートと通知の設定**

..
    Users can set their notification and alert preferences by selecting My Notification Preferences from their header menu.

ユーザーは、ヘッダーメニューの "My Notification Preferences" から通知やアラートを設定できます。

..
   User Preferences

.. figure:: ./images/notifications_6.png
   :alt: User Preferences
   :align: center

   ユーザー設定

..
    You will notice that users have an additional “Screen” delivery mechanism for both their alerts and notifications. The endpoint for Screen notifications is the enStratus console - that is to say, alerts and notifications with the Screen preference ticked will be delivered to the footer of the enStratus console and the Console > Alerts page. See Screen Notifications below for more information.

ユーザーには、アラートと通知の両方に拡張の "スクリーン" 配信システムがあることに気付くでしょう。スクリーン通知のエンドポイントは、enStratus コンソールです。つまり、スクリーン設定で色分けしたアラートと通知は、enStratus コンソールのフッターと "Console > Alerts" ページに配信されます。詳細は次で紹介する "スクリーン通知" を参照してください。

..
    In the following example, any event on any resource (ANY.ANY) will trigger a Screen notification. FIREWALL.CREATE will trigger an Email notification, SERVER.CREATE will trigger a Topic notification, and FIREWALL.UPDATE, FIREWALL.DELETE, and SERVER.DELETE will trigger SMS notifications.

次の例では、任意のリソース上の任意のイベント (ANY.ANY) が、スクリーン通知をトリガーします。FIREWALL.CREATE は、E メール通知を、SERVER.CREATE はトピック通知を、FIREWALL.UPDATE, FIREWALL.DELETE, SERVER.DELETE は SMS 通知をトリガーします。

.. figure:: ./images/notifications_7.png
   :alt: User Preferences
   :align: center

..
    Screen Notifications
    ~~~~~~~~~~~~~~~~~~~~

スクリーンの通知
~~~~~~~~~~~~~~~~

..
    Users will see Screen notifications in two places in the enStratus console: in the lower left-hand footer on every page, and at Console > Alerts.

ユーザーは enStratus コンソールの2箇所でスクリーン通知を参照できます。全てのページの左下のフッターと "Console > Alerts" ページです。

..
   Screen Notifications

.. figure:: ./images/notifications_8.png
   :alt: Screen Notifications
   :align: center

   スクリーン通知

..
    Clicking on the footer notifications menu for a quick view of notifications. To delete a notification, mouse over it in the menu and click the X. If you want to clear all notifications quickly, click the Clear All Alerts link. You will be prompted to confirm you want to clear notifications of all severity across all your accounts.

通知のクイックビューとしてフッター通知メニューをクリックします。通知を削除するには、マウスをメニューの通知上に移動して X をクリックしてください。全ての通知をすぐに消去したいなら、"Clear All Alerts" リンクをクリックしてください。全てのアカウントに対して、全ての重要度の通知を消去するかを確認するプロンプトが表示されます。

..
    For more detail on notifications, click the View All link in the notification menu. This will bring you to the Console > Alerts page.

通知の詳細については、通知メニューの "View All" リンクをクリックしてください。すると、"Console > Alerts" ページに移動します。

..
   Alert or Notification details

.. figure:: ./images/notifications_9.png
   :alt: Details
   :align: center

   アラートや通知の詳細

..
    On this page you can mark alerts read and delete them individually or in bulk. If you click the “show more” link in Subject column, you will see more detail about the notification or alert.

このページでは、アラートの読み込みや削除を個別、または一括で選択できます。"Subject" カラムの "show more" リンクをクリックすると、通知やアラートについての詳細が分かります。
