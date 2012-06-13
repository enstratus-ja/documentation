calculateAgentData
------------------

..
    Name
    ~~~~

名称
~~~~

..
    calculateAgentData - Shell script called periodically to create a properties file with resource utilization

calculateAgentData - リソースの使用状況を含むプロパティファイルを作成するために定期的に呼ばれるシェルスクリプト

..
    Synopsis
    ~~~~~~~~

構文
~~~~

calculateAgentData PROPSFILE

..
    Description
    ~~~~~~~~~~~

説明
~~~~

..
    enStratus calls this script periodically to recalculate resource usage on the server. The
    script prints out a file in the form: property=value

enStratus は、サーバー上のリソースの使用状況を定期的に集計するためにこのスクリプトを実行します。このスクリプトは property=value という形式でファイルに出力します。

..
    It is expected to output the following properties:

次のプロパティを出力します:

..
    * cpuCount - current number of CPU cores
    * cpuLoad - current server load
    * cpuUtilization - utilization of the server (or, alternately, cpuUser and cpuSys)
    * currentRam - amount of RAM currently in use (in MB)
    * maxRam - total RAM on the system (in MB)
    * processes - current number of processes executing on the server
    * deviceTotal.DEVICE - total disk space in GB on a device (example: deviceTotal.sdh=10)
    * deviceUsed.DEVICE - total disk space in GB in use on a device (example: deviceUsed.sdh=5

* cpuCount - 現在の CPU コアの数
* cpuLoad - 現在のサーバーの負荷
* cpuUtilization - サーバーの使用率 (または、その代わりに cpuUser と cpuSys)
* currentRam - 使用中の RAM (MB)
* maxRam - システムの合計 RAM (MB)
* processes - 現在のサーバーで実行中のプロセス数
* deviceTotal.DEVICE - デバイスの総ディスク容量 (GB)（例: deviceTotal.sdh=10）
* deviceUsed.DEVICE - デバイスで使用中の合計ディスク容量 (GB)（例: deviceUsed.sdh=5)

..
    Options
    ~~~~~~~

オプション
~~~~~~~~~~

PROPSFILE
    ..
        Output file to store the performance data. By default is /mnt/tmp/stats.properties

    パフォーマンスデータを保存する出力ファイルです。デフォルトでは /mnt/tmp/stats.properties です。

..
    Examples
    ~~~~~~~~

例
~~

calculateAgentData /mnt/tmp/stats.properties

..
    Invocation
    ~~~~~~~~~~

起動
~~~~

..
    This script is called periodically by the enstratus agent and its content sent to the
    provisioning server.

このスクリプトは、enStratus エージェントが周期的に実行して、その内容はプロビジョニングされたサーバーへ送られます。

..
    Dependencies
    ~~~~~~~~~~~~

依存関係
~~~~~~~~

..
    * Basic performance Unix tools:

* 基本的な Unix のパフォーマンスツール

..
    Permission
    ~~~~~~~~~~

権限
~~~~

..
    It is called by the enstratus user.

enstratus ユーザーが実行します。

..
    Overrides
    ~~~~~~~~~

オーバーライド
~~~~~~~~~~~~~~

..
    Override: No

オーバーライド: 不可

..
    Replace: Yes

置き換え: 可
