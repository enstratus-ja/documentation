..
    Init Scripts
    ------------

Init スクリプト
---------------

..
    Each service should have installed an associated init script, located in /etc/init.d/

各サービスは、/etc/init.d/ に置く init スクリプトに関連付けてインストールします。

..
    enStratus Init Scripts
    ~~~~~~~~~~~~~~~~~~~~~~

enStratus Init スクリプト
~~~~~~~~~~~~~~~~~~~~~~~~~

..
    +----------------+----------------------------------+-------------+
    | Component      | Init Script                      | Usage       |
    +================+==================================+=============+
    | Key Management | /etc/init.d/enstratus-km         | start, stop |
    +----------------+----------------------------------+-------------+
    | Dispatcher     | /etc/init.d/enstratus-dispatcher | start, stop |
    +----------------+----------------------------------+-------------+
    | Monitor        | /etc/init.d/enstratus-monitor    | start, stop |
    +----------------+----------------------------------+-------------+
    | Worker         | /etc/init.d/enstratus-worker     | start, stop |
    +----------------+----------------------------------+-------------+
    | Console        | /etc/init.d/enstratus-console    | start, stop |
    +----------------+----------------------------------+-------------+

.. tabularcolumns:: |l|l|l|

+------------------+----------------------------------+----------------+
| コンポーネント   | Init スクリプト                  | 使用法         |
+==================+==================================+================+
| 鍵管理           | /etc/init.d/enstratus-km         | start, stop    |
+------------------+----------------------------------+----------------+
| ディスパッチャー | /etc/init.d/enstratus-dispatcher | start, stop    |
+------------------+----------------------------------+----------------+
| モニター         | /etc/init.d/enstratus-monitor    | start, stop    |
+------------------+----------------------------------+----------------+
| ワーカー         | /etc/init.d/enstratus-worker     | start, stop    |
+------------------+----------------------------------+----------------+
| コンソール       | /etc/init.d/enstratus-console    | start, stop    |
+------------------+----------------------------------+----------------+
