..
    enStratus Jobs
    --------------

.. _enstratus_jobs:

enStratus ジョブ
----------------

..
    enStratus spawns many jobs, the server jobs will sometimes run interminably, here's how to
    fix that:

enStratus は、多くのジョブを生成します。その中でサーバージョブはたまに終了しないときがあります。ここではその対応方法を説明します。

..
    You can mark any job as complete (or, more likely, just delete them outright) from the
    enstratus_job table.

enstratus_job テーブルから任意のジョブを完了としてマークできます (ほとんどは単純にすぐ削除するだけ)

.. note::
   ..
       The enstratus_job table is in the provisioning database.

   enstratus_job テーブルは、プロビジョニングされたデータベースです。

..
    Deleting Old Jobs
    ~~~~~~~~~~~~~~~~~

古いジョブの削除
~~~~~~~~~~~~~~~~

..
    Run something like this to just get rid of weird old ones:

単純に古いジョブを取り除くには、次のように実行してください:

.. code-block:: mysql

   select *,from_unixtime(start_timestamp/1000) as started from enstratus_job where 
   start_timestamp < ((UNIX_TIMESTAMP() - 100000) * 1000) ;

..
    verify that those are ones to get rid of.  (Ones that are a bit older than 1 day.)  

この中から削除する対象 (1日以上古いもの) を調べます。 

..
    Then:

それから:

.. code-block:: mysql

  delete from enstratus_job where start_timestamp < ((UNIX_TIMESTAMP() - 100000) * 1000) ;

..
    Deleting All Jobs
    ~~~~~~~~~~~~~~~~~

全てのジョブの削除
~~~~~~~~~~~~~~~~~~

..
    No harm will come to the system, though it might confuse some users.

ユーザーを混乱させるかもしれませんが、システムには悪影響を及ぼしません。

.. code-block:: mysql

   delete from enstratus_job where end_timestamp is NULL;
