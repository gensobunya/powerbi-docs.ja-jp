---
title: オンプレミス データ ゲートウェイ
description: これは Power BI のオンプレミス データ ゲートウェイの概要です。 このゲートウェイを使用し、DirectQuery データ ソースを操作できます。 また、このゲートウェイを使用し、オンプレミス データでクラウド データセットを更新できます。
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
LocalizationGroup: Gateways
ms.date: 06/05/2018
ms.openlocfilehash: b56134314b9396dff1b965786e65e62129e5e7b9
ms.sourcegitcommit: 9c3a9ec14c111d766ef5703366c316e72f6e588f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45558449"
---
# <a name="on-premises-data-gateway"></a>オンプレミス データ ゲートウェイ

オンプレミス データ ゲートウェイはブリッジとして機能します。オンプレミス データ (クラウドにないデータ) と Power BI、Microsoft Flow、Logic Apps、PowerApps サービスの間で迅速かつ安全にデータを転送します。

1 つのゲートウェイを複数のサービスで同時に使用できます。 PowerApps と共に Power BI を使用している場合、1 つのゲートウェイを両方に使用できます。 サインインに使用したアカウントによって決まります。

> [!NOTE]
> オンプレミス データ ゲートウェイは、すべてのモードでデータ圧縮およびトランスポートの暗号化を実行します。

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-requirements-include.md)]

### <a name="limitations-of-analysis-services-live-connections"></a>Analysis Services のライブ接続の制限事項

表形式または多次元インスタンスに対してライブ接続を使用することはできません。

| **サーバーのバージョン** | **必要な SKU** |
| --- | --- |
| 2012 SP1 CU4 以降 |Business Intelligence と Enterprise SKU |
| 2014 |Business Intelligence と Enterprise SKU |
| 2016 |Standard SKU 以上 |

* セル レベルの書式設定および変換機能はサポートされていません。
* アクションおよび名前付きセットは Power BI には公開されませんが、アクションまたは名前付きセットも含む多次元キューブに接続し、ビジュアルおよびレポートを作成することはできます。

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="download-and-install-the-on-premises-data-gateway"></a>オンプレミス データ ゲートウェイをダウンロードし、インストールする

ゲートウェイをダウンロードするには、[ダウンロード] メニューで **[データ ゲートウェイ]** を選択します。 [オンプレミス データ ゲートウェイ](http://go.microsoft.com/fwlink/?LinkID=820925)をダウンロードします。 

このセクションで説明されているように、オンプレミス データ ゲートウェイの更新は、ゲートウェイの再インストールによって実現されます。 (再インストールして) ゲートウェイを更新しても、既存のゲートウェイの設定は保持されます。

![](media/service-gateway-onprem/powerbi-download-data-gateway.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-install-include](./includes/gateway-onprem-install-include.md)]

## <a name="install-the-gateway-in-personal-mode"></a>個人モードでゲートウェイをインストールする

> [!NOTE]
> 個人用バージョンのゲートウェイは Power BI でのみ動作します。

Personal Gateway をインストールしたら、**Power BI Gateway - Personal 構成ウィザード**を起動する必要があります。

![](media/service-gateway-onprem/personal-gateway-launch-configuration.png)

Power BI にサインインし、クラウド サービスにゲートウェイを登録する必要があります。

![](media/service-gateway-onprem/personal-gateway-signin.png)

また、Windows サービスを実行するユーザー名とパスワードを入力する必要があります。 自分の Windows アカウントとは別のアカウントを指定できます。 このアカウントを使用して、ゲートウェイ サービスが実行されます。

![](media/service-gateway-onprem/personal-gateway-windows-service.png)

インストールの完了後、Power BI 内のデータセットに移動し、オンプレミス データ ソースの資格情報を入力する必要があります。

<a name="credentials"></a>

## <a name="storing-encrypted-credentials-in-the-cloud"></a>暗号化された資格情報をクラウドに格納する

データ ソースをゲートウェイに追加する場合は、そのデータ ソースの資格情報を指定する必要があります。 データ ソースへのすべてのクエリは、これらの資格情報を使用して実行されます。 資格情報は、クラウド内で解読されないように、クラウドに格納される前に非対称暗号化を使用して安全に暗号化されます。 資格情報は、データ ソースにアクセスするときに、ゲートウェイを実行しているオンプレミスのコンピューターに送信されて暗号化が解除されます。

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

<!-- How the gateway works -->
[!INCLUDE [gateway-onprem-how-it-works-include](./includes/gateway-onprem-how-it-works-include.md)]

## <a name="limitations-and-considerations"></a>制限事項と考慮事項

* [Azure Information Protection](https://docs.microsoft.com/microsoft-365/enterprise/protect-files-with-aip
) は現在サポートされていません
* [Access Online](https://products.office.com/en-us/access) は現在サポートされていません。

## <a name="tenant-level-administration"></a>テナント レベルの管理

現在、テナント管理者が、他のユーザーがインストールおよび構成しているすべてのゲートウェイを管理できる場所がありません。  テナント管理者である場合は、組織内のユーザーに対して、インストールされているすべてのゲートウェイに管理者として追加することを求めるようお勧めします。 これにより、[ゲートウェイ設定] ページまたは [PowerShell コマンド](https://docs.microsoft.com/power-bi/service-gateway-high-availability-clusters#powershell-support-for-gateway-clusters)を介して組織内のすべてのゲートウェイを管理することができます。 

## <a name="enabling-outbound-azure-connections"></a>Azure の送信接続を有効にする

オンプレミス データ ゲートウェイは、クラウド接続の際に Azure Service Bus に依存します。それに応じて、関連付けられている Azure リージョンへの送信接続を確立します。 既定では、これは Power BI テナントの場所となります。 「[Power BI テナントの場所](https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-where-is-my-tenant-located/)」を参照してください。
送信接続がファイアウォールでブロックされている場合は、オンプレミス データ ゲートウェイから関連付けられている Azure リージョンへの送信接続を許可するようにファイアウォールを構成する必要があります。 各 Azure データ センターの IP アドレス範囲の詳細については、「[Microsoft Azure Datacenter IP Ranges](https://www.microsoft.com/en-us/download/details.aspx?id=41653)」 (Microsoft Azure データセンターの IP 範囲) を参照してください。
> [!NOTE]
> IP アドレスの範囲は時間の経過と共に変わる可能性があるため、必ず最新情報を定期的にダウンロードしてください。 

## <a name="troubleshooting"></a>トラブルシューティング

ゲートウェイをインストールおよび構成するときに問題が発生する場合は、「[オンプレミス データ ゲートウェイのトラブルシューティング](service-gateway-onprem-tshoot.md)」をご覧ください。 ファイアウォールで問題が発生していると思われる場合は、トラブルシューティング記事の[ファイアウォールまたはプロキシ](service-gateway-onprem-tshoot.md#firewall-or-proxy)に関するセクションを参照してください。

ゲートウェイでプロキシの問題が発生していると思われる場合は、「[Power BI Gateway のプロキシ設定を構成する](service-gateway-proxy.md)」をご覧ください。

## <a name="next-steps"></a>次の手順

[データ ソースの管理 - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[データ ソースの管理 - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[データ ソースの管理 - SQL Server](service-gateway-enterprise-manage-sql.md)  
[データ ソースの管理 - Oracle](service-gateway-onprem-manage-oracle.md)  
[データ ソースの管理 - インポート/スケジュールされた更新](service-gateway-enterprise-manage-scheduled-refresh.md)  
[オンプレミス データ ゲートウェイの詳細](service-gateway-onprem-indepth.md)  
[オンプレミス データ ゲートウェイ (個人用モード) - 新しいバージョンのパーソナル ゲートウェイ](service-gateway-personal-mode.md)
[オンプレミス データ ゲートウェイのプロキシ設定を構成する](service-gateway-proxy.md)  

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。