API
---

..
    The enStratus console is a tomcat service installed to /services/api.

enStratus コンソールは、/services/api にインストールされる tomcat サービスです。

..
    Starting API
    ~~~~~~~~~~~~

API の開始
~~~~~~~~~~

.. code-block:: bash

	/etc/init.d/enstratus-api start

..
    There should be a java process listening on port 15000, for a default installation.

デフォルトだと、15000番ポートでリクエストを受け付ける java プロセスが開始します。

.. code-block:: bash

  netstat -tnlup | grep java
  tcp6       0      0 :::15000                :::*                    LISTEN      5647/java       
  tcp6       0      0 127.0.0.1:16099         :::*                    LISTEN      5647/java  

..
    Stopping API
    ~~~~~~~~~~~~

API の停止
~~~~~~~~~~

.. code-block:: bash

	/etc/init.d/enstratus-api stop

