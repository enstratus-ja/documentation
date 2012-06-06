..
    IP Addresses
    ------------

.. _saas_ipaddresses:

IP アドレス
-----------

..
    Overview
    ~~~~~~~~

概要
~~~~

..
    *IP Addresses allow for reservation of static ip addresses which can then be assigned to running servers.*

*静的な IP アドレスを予約しておき、実行中のサーバーに割り当てられます。*

.. note::
   ..
       IP address reservation is a feature not available in all clouds. If it's not a
       feature supported by your cloud provider, enStratus will not present it in the console.

   IP アドレスの予約は、全てクラウドで利用できません。クラウドプロバイダーが対応していないなら、enStratus はコンソールに表示しません。

..
    To reserve an IP Address, click on + reserve_address in the menu window and select Reserve
    IP Address. A new IP address will be added to the list of Active Addresses.

IP アドレスを予約するには、メニュー画面の "+ reserve_address" をクリックして、"Reserve IP Address" を選択します。"Active Addresses" リストに新規の IP アドレスが追加されます。

.. note::
   ..
       In the Amazon cloud, there is a limit of 5 reserved IP addresses. To reserve
       more, you must contact Amazon Web Services.

   Amazon のクラウドでは、予約済 IP アドレスに5個の制限があります。もっと多く予約するには、Amazon Web サービスに問い合わせる必要があります。

..
    Once the IP address has been reserved it is available for use by assigning it to a running
    server. To assign the IP address to a server, select the green actions button and choose
    assign. A dialog box will appear with a dropdown list of available servers. Select your
    server from the list and choose Assign address. It will take a few moments for the
    assignment to be made.

IP アドレスが予約されると、実行中のサーバに割り当てて利用できます。サーバーに IP アドレスを割り当てるには、アクションボタンから割り当てを選択します。利用可能なサーバーのドロップダウンリストをもつダイアログボックスが表示されます。そのリストからサーバーを選択し、"Assign address" を選択します。割り当てが完了するには少し時間がかかります。

..
    If an addresses is already assigned to a server and is set for removal instead, click on
    the actions button and choose the release option. This action will also take a few
    moments.

IP アドレスがすでにサーバーに割り当てられ、代わりに削除する設定を行う場合、アクションボタンをクリックして "release" オプションを選択します。このアクションも少し時間がかかります。

..
    Hint: Unused reserved IP addresses still cost money even though they are not assigned to
    running server. To delete an IP address, click on the actions button and choose delete.
    Confirm the deletion in the resulting dialog box and the IP address will be removed from
    your account.

ヒント: 未使用の予約済 IP アドレスは、実行中のサーバーに割り当てられてなくてもコストが発生します。IP アドレスを削除するには、アクションボタンをクリックして  "削除" を選択します。表示されるダイアログボックスで削除されたことを確認すると、アカウントから IP アドレスが削除されます。
