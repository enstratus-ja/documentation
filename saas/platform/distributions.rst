.. _saas_distributions:

ディストリビューション
----------------------

..
    Distributions
    -------------

..
    enStratus supports cloud based content distribution networks or content delivery networks
    (CDN) through enStratus Distributions. Distributions allow users to distribute content
    from cloud storage quickly and efficiently to end users in the cloud.

enStratus は、"enStratus Distributions" ページで、クラウドベースのコンテンツディストリビューションネットワークやコンテンツデリバリーネットワーク (CDN) に対応しています。Distributions は、コンテンツをクラウドストレージから素早く効率的にクラウドのエンドユーザーへ配布できます。

..
    enStratus currently supports Limelight Networks' CDN through the Rackspace cloud and the
    Amazon Web Services CDN CloudFront. CloudFront allow users to distribute content from
    Amazon S3 storage and Limelight Networks allows users to distribute content from Rackspace
    Cloud Files.

現在、enStratus は、Rackspace クラウド経由の Limelight Networks の CDN と、Amazon Web Services CDN CloudFront に対応しています。CloudFront は Amazon S3 ストレージのコンテンツを、Limelight Networks は Rackspace のクラウドファイルからコンテンツを配布します。

..
    To create a new distribution in enStratus click on Platform > Distributions then click
    +Create Distribution.

enStratus の新規ディストリビューションを作成するには、プラットフォームで "Platform > Distributions" から "+Create Distribution" をクリックします。

..
    Screenshot

スクリーンショット

..
    Note: to create a new distribution you must have a pre-existing directory in Platform >
    Files. Click here for more detail.

新規ディストリビューションを作成するには、"Platform > Files" にディレクトリが存在している必要があることに注意してください。

..
    The Name field is where you specify a custom domain name for your distribution. (e.g.
    example.cloudfront.net)

**Name** フィールドは、ディストリビューション用のカスタムドメインの任意の名称です (例 example.cloudfront.net) 。

..
    The Aliases field allows you to map comma delimited aliases to the specific domain name.

**Aliases** フィールドは、特定ドメイン名にカンマで区切りの別名をマッピングします。

..
    The Select a directory drop-down contains a list of all root-level directories located on
    the Platform > Files page of the enStratus console. The directory that is selected for the
    distribution is mapped to the domain name you created.

"Select a directory" のドロップダウンは、enStratus コンソールの "Platform > Files" ページに置かれたルートレベルの全リストを含みます。配布用に選択されたディレクトリは、作成されたドメイン名にマップされます。

..
    Clicking the actions tab next to your newly created distribution will provide you with the
    options to edit, delete, or activate/deactivate the distribution.

新しく作成したディストリビューションの横にある "actions" タブをクリックすると、編集、削除、有効/無効のプションが提供されます。
