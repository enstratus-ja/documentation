format
------

..
    Function
    ~~~~~~~~

機能
~~~~

..
    It creates a filesystem in a given physical or logical storage volume. Additionally it adds an entry for that volume in /etc/fstab so the volume can be mounted easily. Actual volume mount is performed by the mount script.

所定の物理または論理ストレージボリュームにファイルシステムを作成します。さらに、このボリュームを /etc/fstab のエントリに追加して、簡単にマウントできるようにします。実際にボリュームのマウントは、このスクリプトにより行われます。

..
    Usage
    ~~~~~

使用法
~~~~~~

format DEVICE_ID FILE_SYSTEM MOUNT_POINT ENCRYPTED


DEVICE_ID
    ..
        Last part of the Linux device name (ie sdh for /dev/sdh or data for /dev/mapper/data ) . Generally this parameter is obtained automatically from the cloud provider.

    Linux デバイス名の最後の部分です (例えば /dev/sdh なら sdh、/dev/mapper/data なら data) 。一般的にこのパラメーターは、クラウドプロバイダーから自動的に取得されます。

FILE_SYSTEM
    ..
        File system to be created. Most popular Linux filesystems are available (xfs,ext2,ext3,ext4) provided the server image includes support for them. By default enstratus will use xfs

    作成されるファイルシステムです。一般的に使われている Linux ファイルシステム (xfs,ext2,ext3,ext4) が利用できます。これらのファイルシステムのサポートはサーバーイメージで提供されます。デフォルトでは enstratus は xfs を使います。

MOUNT_POINT
    ..
        Empty directory where the formatted volume will be mounted

    フォーマット済みのボリュームをマウントする空のディレクトリです。

ENCRYPTED
    ..
        Whether or not the volume has been decrypted by enstratus. That is required to find the correct device name and set suitable options in /etc/fstab

    enStratus がボリュームを複合化するかどうかの設定です。正しいデバイス名と /etc/fstab の適切なオプションを設定する必要があります。

..
    Invocation
    ~~~~~~~~~~

起動
~~~~

..
    This script is called when:

このスクリプトは次のときに実行されます:

..
    * If a volume is created when manually launching a server from the Machine Images page. In this case the mount point and file system can be set by the user.
    * When a server is launched within a deployment and the launch configuration has been set to automatically create a volume. In this case volume is mounted in /mnt/services and given a xfs filesystem.

* "Machine Images" ページから手動でサーバーを起動して、ボリュームが作成されるときです。このとき、実行ユーザーがマウントポイントとファイルシステムを設定します。
* サーバーがデプロイメントで起動されて、起動構成が自動的にボリュームを作成するときです。このとき、ボリュームが /mnt/services に xfs ファイルシステムでマウントされます。

..
    Dependencies
    ~~~~~~~~~~~~

依存関係
~~~~~~~~

* sudo
* mkfs utility for the selected filesystem, that's is mkfs.xfs for XFS support, mkfs.ext3 for ext3
* Kernel modules required for mounting the filesystem

..
    Permission
    ~~~~~~~~~~

権限
~~~~

..
    It is called by the enstratus user. It needs sudo authority for creating a filesystem and editing the /etc/fstab file.

enstratus ユーザーが実行します。ファイルシステムを作成して、/etc/fstab ファイルを編集するために sudo 権限が必要です。

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
