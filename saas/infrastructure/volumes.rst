..
    Volumes
    -------

.. _saas_volumes:

ボリューム
----------

..
    Overview
    ~~~~~~~~

概要
~~~~

..
    Volumes represent block storage. Conceptually, storage devices can be used to store data in a persistent manner in the cloud.

ボリュームは、ブロックストレージを表します。概念的には、ストレージデバイスは、クラウド内のデータを永続的な方法で格納するために使えます。

..
    Creating Volumes
    ~~~~~~~~~~~~~~~~

ボリュームの作成
~~~~~~~~~~~~~~~~

..
    To create a new volume, navigate to Infrastructure > Volumes. If volumes had been
    previously created either within enStratus or via the cloud provider, they will be listed
    in the volumes table. Select +create_volume and complete the resulting dialog box.

新規のボリュームを作成するには、"Infrastructure > Volumes" に移動します。ボリュームがそれまでに enStratus またはクラウドプロバイダーのいずれかを介して作成されていた場合、それらがボリュームテーブルに表示されます。"+create_volume" を選択し、表示されるダイアログボックスに記入します。

..
   Create Volume

.. figure:: ./images/createVolume.png
   :height: 300px
   :width: 400 px
   :scale: 95 %
   :alt: Create Volume
   :align: center

   ボリュームの作成

..
    The name of the volume is a logical name that will be used within enStratus to reference
    the volume. The size of the volume is should be between 1 and 1000 gigabytes (1 Tb).

ボリュームの名前は enStratus 内でボリュームを参照するために使う論理名です。ボリュームのサイズは 1-1000 ギガバイト (1 TB) の範囲内です。

..
    The Zone in which a volume is created is important because volumes may only be attached to
    servers in the same zone. Billing code and group complete the creation options for a
    volume.

ボリュームは同じゾーン内のサーバーのみに取り付けられるため、ボリュームが作成されるゾーンは重要です。課金コードとグループといったボリュームの作成オプションを記入します。

..
    Volume creation takes only a few minutes to complete. Once the volume is created it will
    be added to the list of volumes. Since newly created volumes are not attached to a server,
    the Device and Current Server columns will be blank.

ボリュームの作成が完了するまでほんの数分しかかかりません。一度ボリュームが作成されると、ボリュームのリストに追加されます。新しく作成したばかりのボリュームは、サーバーに接続されていないので、デバイスと現在のサーバーのカラムは空白になります。

..
   Volume Created

.. figure:: ./images/finishedVolume.png
   :height: 400px
   :width: 1600 px
   :scale: 50 %
   :alt: Volume Created
   :align: center

   ボリュームの作成

..
    Attaching Volumes
    ~~~~~~~~~~~~~~~~~

ボリュームの接続
~~~~~~~~~~~~~~~~

..
    Volumes and servers must share an availability zone for volume attachment to succeed.
    Volumes are attached as block storage devices and are neither partitioned nor formatted
    when attached. enStratus allows for automated attachment, formatting, and mounting of new
    volumes only when starting a new server.

ボリュームとサーバーは、ボリュームの接続を行うために可用性ゾーンを共有する必要があります。ボリュームがブロックストレージデバイスとして接続されるなら、パーティション作成もフォーマットも接続時に行われません。enStratus は、新規サーバーを起動する場合にのみ、自動接続、フォーマット、新規ボリュームの追加を行います。

..
    To attach a volume to a server, select the volume for attachment and select the green
    actions button. The only required information to attach a volume is the name of the server
    to which the volume will be attached. The list of servers that share an availability zone
    will populate the dropdown selector.

サーバーへボリュームを接続するには、接続するボリュームを選択し、アクションボタンを選択します。ボリュームを接続するための唯一の必要な情報はボリュームが接続されるサーバー名です。可用性ゾーンを共有するサーバーのリストはドロップダウンセレクターに存在します。

..
    Optionally, a device name may be selected for the volume. In this case, I have chosen a
    device name of sdh, which means the device will appear as /dev/sdh on the server:

オプションとして、デバイス名を、ボリュームのために選択できます。この例では、選択したデバイス名 sdh が /dev/sdh として表示されます。

.. code-block:: bash

  p335@ApplicationServer:~$ sudo fdisk -l

  Disk /dev/sdh: 2147 MB, 2147483648 bytes 255 heads, 63 sectors/track, 261 cylinders Units
  = cylinders of 16065 * 512 = 8225280 bytes Sector size (logical/physical): 512 bytes / 512
  bytes I/O size (minimum/optimal): 512 bytes / 512 bytes Disk identifier: 0x00000000

  Disk /dev/sdh doesn't contain a valid partition table

..
    Once the volume is attached, it can be considered and treated somewhat like an external
    hard drive attached to the server. Standard hard drive activities are available including
    partitioning, formatting, and mounting.

ボリュームが接続されると、外部ハードドライブがサーバーに接続されているようにみなせます。パーティショニング、フォーマット、マウントを含む標準的なハードディスクドライブの機能を利用できます。

..
    Creating Snapshots
    ~~~~~~~~~~~~~~~~~~

スナップショットの作成
~~~~~~~~~~~~~~~~~~~~~~

..
    Snapshots are created from volumes and volumes are created from snapshots.

スナップショットはボリュームから作成され、ボリュームがスナップショットから作成されます。

..
    A snapshot of a volume represents a differential backup of the data contained on the
    volume. This means that only the blocks that have changed are saved each time a snapshot
    is created. To create a snapshot, select the green actions button for the volume, and
    choose make_snapshot. The only required information to create the snapshot is a logical
    name for the snapshot. Once the snapshot is saved, the snapshot will appear in the
    snapshots page in the enStratus console.

ボリュームのスナップショットはボリュームに含まれるデータの差分バックアップを表します。これは、変更されたブロックのみがスナップショットを作成する毎に保存されることになります。スナップショットを作成するには、ボリュームのアクションボタンを選択し、"make_snapshot" を選択します。スナップショットを作成するために必要な情報は、スナップショットの論理名のみです。スナップショットが保存されると、スナップショットは enStratus コンソールのスナップショットのページで表示されます。

..
    Deleting Volumes
    ~~~~~~~~~~~~~~~~

ボリュームの削除
~~~~~~~~~~~~~~~~

..
    To delete a volume, click on the green action button associated with the volume and choose
    delete. A dialog box will prompt you to confirm the action and the volume will be removed
    from the volumes list.

ボリュームを削除するには、ボリュームに関連付けられたアクションボタンをクリックして削除を選択します。ダイアログボックスに、ボリュームリストからボリュームを削除するための、ボリュームとアクションを確認するように表示されます。

..
    Volume Strategies
    ~~~~~~~~~~~~~~~~~

ボリュームの戦略
~~~~~~~~~~~~~~~~

..
    Volume storage is often persistent beyond the life of the server to which it was attached.
    This makes volumes a very useful item for managing data storage in the cloud. In a
    high-availability failure-tolerant automated environment, enStratus leverages volumes to
    restore applications to an operational state without data loss.

ボリュームストレージは、多くの場合、接続されたサーバーの寿命よりも永続的です。これは、ボリュームがクラウドのデータストレージを管理するとても便利な要素になります。高可用性のある障害トレラント (failure-tolerant) 自動化環境では、enStratus はデータを失うことなく使える状態にアプリケーションを復元するためにボリュームを活用します。
