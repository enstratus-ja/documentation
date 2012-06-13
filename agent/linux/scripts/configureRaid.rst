configureRaid
-------------

..
    NAME
    ~~~~

名称
~~~~

..
    configureRaid - Creates RAID devices

configureRaid - RAID デバイスを作成する

..
    Synopsis
    ~~~~~~~~

構文
~~~~

configureRaid DEVICE_ID VOLUMES...

..
    Description
    ~~~~~~~~~~~

説明
~~~~

..
    It creates a RAID device from a list of storage devices. Currently only RAID 0 (striped) volumes are supported 

ストレージデバイスの一覧から RAID デバイスを作成します。現在は RAID 0 (ストライピング) ボリュームのみに対応しています。

..
    Options
    ~~~~~~~

オプション
~~~~~~~~~~

DEVICE_ID
    ..
        Last part of the Linux device name for the RAID device to be created (md0 for /dev/md0 by default)

    作成した RAID デバイスの Linux デバイス名の最後の部分です (デフォルトだと /dev/md0 の md0) 。

VOLUMES	
    ..
        List of devices to be added to the RAID volume

    RAID ボリュームに追加するデバイスの一覧

..
    Examples
    ~~~~~~~~

例
~~

/enstratus/bin/configureRaid md0 sdh sdi sdj
	Creates the RAID 0 device /dev/md0 from volumes /dev/sdh, /dev/shi and /dev/sdj

..
    Invocation
    ~~~~~~~~~~

起動
~~~~

..
    This script is called when:

このスクリプトは次のときに実行されます:

..
    * If a volume is created when manually launching a server from the Machine Images page and
      a RAID Level other that None is selected.

* "Machine Images" ページから手動でサーバーを起動して、"RAID Level" に "None" 以外を選択したとき

..
    Dependencies
    ~~~~~~~~~~~~

依存関係
~~~~~~~~

* sudo
* mdadm
* md kernel module

..
    Permission
    ~~~~~~~~~~

権限
~~~~

..
    It is called by the enstratus user. It needs sudo authority for creating the array

enstratus ユーザーが実行します。アレイを作成するために sudo 権限が必要です。

..
    Overrides
    ~~~~~~~~~

オーバーライド
~~~~~~~~~~~~~~

..
    Override: Yes, pre and post

オーバーライド: 可、事前と事後

..
    Replace: Yes

置き換え: 可
