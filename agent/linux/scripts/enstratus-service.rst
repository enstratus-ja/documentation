enstratus-service
~~~~~~~~~~~~~~~~~

..
    Name
    ++++

名称
++++

..
    enstratus-service - Manages the enStratus agent daemon

enstratus-service - enStratus エージェントデーモンを管理する

..
    Synopsis
    ++++++++

構文
++++

enstratus-service ACTION

..
    Description
    +++++++++++

説明
++++

..
    It starts or stops the enStratus agent.

enStratus エージェントを開始したり停止したりします。

..
    Options
    +++++++

オプション
++++++++++

ACTION
    ..
        start for starting the enStratus agent
        stop for stopping the enStratus agent

    start は enStratus エージェントを開始する

    stop は enStratus エージェントを停止する

..
    Examples
    ++++++++

例
++

.. code-block:: sh

	$ /enstratus/bin/enstratus-service stop
	Using CATALINA_BASE:   /enstratus/ws/tomcat
	Using CATALINA_HOME:   /enstratus/ws/tomcat
	Using CATALINA_TMPDIR: /enstratus/ws/tomcat/temp
	Using JRE_HOME:       /usr/java/jdk
	$ /enstratus/bin/enstratus-service start
	Using CATALINA_BASE:   /enstratus/ws/tomcat
	Using CATALINA_HOME:   /enstratus/ws/tomcat
	Using CATALINA_TMPDIR: /enstratus/ws/tomcat/temp
	Using JRE_HOME:       /usr/java/jdk

..
    Invocation
    ++++++++++

起動
++++

..
    This script is called by /etc/init.d/tomcat-enstratus on server boot to start the enStratus agent. It can also be run manually to start/stop the agent.

このスクリプトは /etc/init.d/tomcat-enstratus により enStratus エージェントを開始するためにサーバー起動時に実行します。enStratus エージェントを手動で開始/停止するのにも使えます。

..
    Dependencies
    ++++++++++++

依存関係
++++++++

..
    * enStratus agent requires JDK

* enStratus エージェントは JDK を必要とします

..
    Permission
    ++++++++++

権限
++++

..
    It is launched by the enStratus user.

enstratus ユーザーが実行します。

..
    Overrides
    +++++++++

オーバーライド
++++++++++++++

..
    Override: No

オーバーライド: 不可

..
    Replace: No

置き換え: 不可
