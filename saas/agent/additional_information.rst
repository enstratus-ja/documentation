..
    Additional Information
    ----------------------

.. _agent_additional_information:

追加情報
--------

..
    Updating
    ^^^^^^^^

更新
^^^^

..
    Updating the agent on a Ubuntu/Debian server can be accomplished by using the .deb
    package. The installation routine will detect previously installed versions and do a
    backup, preserving any customizations by preserving the contents of the
    /enstratus/custom/bin directory.

Ubuntu/Debian サーバーのエージェント更新は、deb パッケージから行えます。インストール処理は、以前にインストールしたバージョンを検出して、/enstratus/custom/bin ディレクトリの内容を保存することにより、任意のカスタマイズもバックアップされます。

..
    Extending the Agent
    ^^^^^^^^^^^^^^^^^^^

エージェントの拡張
^^^^^^^^^^^^^^^^^^

..
    Agent scripts are designed to be extended and customized. The scripts located in
    /enstratus/bin are not designed to be edited directly as these scripts are overwritten
    during an upgrade. Instead, use the /enstratus/custom/bin directory to run custom scripts
    before, in place of, and/or after the provided scripts.

エージェントスクリプトは、拡張やカスタマイズが行えるように設計されています。/enstratus/bin のスクリプトは、アップグレード時に上書きされるので、直接編集するようには考えられていません。代わりに、提供されたスクリプトの前後でカスタムスクリプトを実行するには /enstratus/custom/bin ディレクトリを使います。

..
    To run a script before the default enStratus script, place a script called $scriptName-pre
    in the /enstratus/custom/bin directory. To run a script in place of the default enStratus
    script, place a script of the same name in the /enstratus/custom/bin directory. To run a
    script after the default enStratus script, place a script called $scriptName-post in the
    /enstratus/custom/bin directory.

デフォルトの enStratus スクリプトが実行される前にスクリプトを実行するには、$scriptName-pre というファイル名で /enstratus/custom/bin ディレクトリに置きます。デフォルトの enStratus スクリプトの代わりにスクリプトを実行するには、同じファイル名のスクリプトを /enstratus/custom/bin ディレクトリに置きます。デフォルトの enStratus スクリプトが実行された後にスクリプトを実行するには、$scriptName-post というファイル名で /enstratus/custom/bin ディレクトリに置きます。

..
    For example to modify the /enstratus/bin/addUser script do the following:

例えば、/enstratus/bin/addUser スクリプトを修正するには、次のようにします。

..
    /enstratus/custom/bin/addUser - if exists, will completely replace this script 

/enstratus/custom/bin/addUser - 存在する場合、完全にこのスクリプトを置き換える

..
    /enstratus/custom/bin/addUser-pre - if exists, will be executed before this script 

/enstratus/custom/bin/addUser-pre  - 存在する場合、このスクリプトの前に実行される

..
    /enstratus/custom/bin/addUser-post - if exists, will be executed after this script

/enstratus/custom/bin/addUser-post  - 存在する場合、このスクリプトの後に実行される

..
    Starting from Scratch
    ^^^^^^^^^^^^^^^^^^^^^

スクラッチからの開始
^^^^^^^^^^^^^^^^^^^^

..
    At enStratus we use the EC2 images supplied by Alestic www.alestic.com with success. The
    .deb installer has been tested with the latest releases of Ubuntu (10.04) and Debian
    (5.0).

enStratus で Alestic www.alestic.com が提供する EC2 イメージが正常に使えます。この deb インストーラーは、Ubuntu (10.04) と Debian (5.0) の最新リリースでテストされています。

..
    The installation process should work on most flavors of Ubuntu and Debian, if you have
    trouble installing on your own, please contact support at enStratus.

このインストール処理は、Ubuntu と Debian のほとんどのバージョンで動作するはずです。インストール上のトラブルは enStratus サポートへ連絡してください。
