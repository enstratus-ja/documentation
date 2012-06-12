..
    Roles
    -----

.. _saas_roles:

ロール
------

..
    How roles affect users
    ~~~~~~~~~~~~~~~~~~~~~~

ロールがユーザーに与える影響
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    We've been saying that a user 'inherit' access rights from the role assigned
    to the group(s) they are assigned. Roles have very granular access control definitions
    which are useful when defining the type and level of access users in a group should have.
    The enforcement of access controls is done through the enStratus console. A user may see a
    limited set of options when clicking on the actions link for a cloud resource.

これまでユーザーを含むグループに対してロールを割り当て、そのロールからアクセス権を "継承する" と説明してきました。ロールは、非常に細かいアクセス制御の定義を持っており、これはグループ内のユーザーのアクセスレベルと種別を定義するときに便利です。アクセス制御の実行は、enStratus コンソールを経由して行われます。クラウドリソースの "actions" リンクをクリックすると、表示されるオプションが制限されます。

..
    In the SaaS version of enStratus this is the method by which enStratus enforces access
    controls.

enStratus の SaaS 版では、これが enStratus によるアクセス制御の実行方法です。

..
    In an on-premise deployment, customers may choose the option to completely hide cloud
    resources to which a user has no access. Again, this enforcement is done through the
    enStratus console, except in this case if a user has no access to a cloud resource, the
    resource is not presented to the user.

オンプレミスのデプロイ環境では、ユーザーがアクセス権を持たないクラウドリソースを完全に非表示にするオプションも、顧客が選択できます。繰り返しですが、このアクセス制御の実行は enStratus コンソールから行われます。但し、ユーザーがクラウドリソースへのアクセス権を持っていなくて、リソースがユーザに表示されない場合を除きます。
