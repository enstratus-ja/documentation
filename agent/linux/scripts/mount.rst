mount
-----

..
    Name
    ~~~~

名称
~~~~

..
    mount - It mounts a storage device at a directory. 

mount -  ストレージデバイスをディレクトリにマウントする

..
    Description
    ~~~~~~~~~~~

説明
~~~~

..
    It mounts a storage device at a directory. Additional the mount point will be added to the /etc/fstab file so it is mounted automatically on server restart.

ストレージデバイスをディレクトリにマウントします。
サーバーが再起動したときに自動的にマウントされるように、追加のマウントポイントを /etc/fstab ファイルに追加します。

..
    Usage
    ~~~~~

使用法
~~~~~~

mount DEVICE_ID FILE_SYSTEM MOUNT_POINT


DEVICE_ID
    ..
        Last part of the Linux device name (ie sdh for /dev/sdh or data for /dev/mapper/data ) . Generally this parameter is obtained automatically from the cloud provider.

    Linux デバイス名の最後の部分です (例えば /dev/sdh なら sdh、/dev/mapper/data なら data) 。一般的にこのパラメーターは、クラウドプロバイダーから自動的に取得されます。

FILE_SYSTEM
    ..
        File system of the volume to be mounted. It is required to add the mount point to the /etc/fstab file.

    ボリュームにマウントされるファイル システムです。マウントポイントを /etc/fstab ファイルに追加する必要があります。

MOUNT_POINT
    ..
        Empty directory where the volume will be mounted

    ボリュームをマウントする空のディレクトリ

..
    Invocation
    ~~~~~~~~~~

..
    This script is called when:

このスクリプトは次のときに実行されます:

..
    * If a volume is created when manually launching a server from the Machine Images page. In this case the mount point and file system can be set by the user.
    * A Volume is attached to a server in the Volume list page, and the option Automount is selected
    * When a server is launched within a deployment and its Launch Configuration has been set to automatically create a volume. In this case volume is mounted in /mnt/services and given a xfs filesystem.

* "Machine Images" ページから手動でサーバーを起動したときにボリュームが作成される場合です。このとき、実行ユーザーがマウントポイントとファイルシステムを設定します。
* "Volume" 一覧ページでボリュームがサーバーに接続されて、そのオプションである "Automount" が選択されるとき
* サーバーがデプロイメントで起動されて、起動構成が自動的にボリュームを作成するときです。このとき、ボリュームが /mnt/services に xfs ファイルシステムでマウントされます。

..
    Dependencies
    ~~~~~~~~~~~~

依存関係
~~~~~~~~

..
    * sudo
    * Kernel modules required for mounting the filesystem

* sudo
* ファイルシステムをマウントするのに必要な kernel モジュール

..
    Permissions
    ~~~~~~~~~~~

権限
~~~~

..
    It is called by the enstratus user. It needs sudo authority for mounting a filesystem and
    editing the /etc/fstab file. User enstratus will own the mount point and will be writeable
    by the user and group enstratus.

enstratus ユーザーが実行します。ファイルシステムをマウントして /etc/fstab ファイルを編集するために sudo 権限が必要です。enstratus ユーザーは独自のマウントポイントを持ち、その enstratus ユーザーとグループで書き込みます。

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
