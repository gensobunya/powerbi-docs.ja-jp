---
title: 組織で Power BI Premium 容量を監視する
description: Power BI 管理ポータルと Power BI Premium 容量メトリック アプリを使用する
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 08/29/2018
LocalizationGroup: Premium
ms.openlocfilehash: 8e19bc596bef3862dca79ac92ffbd74954a9c756
ms.sourcegitcommit: 6be2c54f2703f307457360baef32aee16f338067
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "43300163"
---
# <a name="monitor-power-bi-premium-capacities-in-your-organization"></a>組織で Power BI Premium 容量を監視する

この記事では、Power BI Premium 容量のメトリックの監視の概要について説明します。 容量の使用状況を監視することで、情報に基づいた方法で容量を監視することができます。 

Power BI Premium 容量メトリック アプリまたは管理ポータルで容量を監視できます。 より多くの詳細が表示されるためアプリをお勧めしますが、この記事では両方のオプションについて説明します。

## <a name="install-the-premium-capacity-metrics-app"></a>Premium 容量メトリック アプリのインストール

[Premium 容量メトリック アプリ](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics)に直接移動するか、Power BI の他のアプリと同じようにインストールします。

> [!IMPORTANT]
> このアプリをインストールして使用するには、少なくとも 1 つの容量の容量管理者である必要があります。 Power BI 管理者であるだけでは不十分です。 

1. Power BI で **[アプリ]** をクリックします。

    ![アプリに移動する](media/service-admin-premium-monitor-capacity/apps.png)

2. 右側にある **[アプリの取得]** をクリックします。

3. **[アプリ]** カテゴリで、**[Power BI Premium Capacity Metrics app]\(Power BI Premium 容量メトリック アプリ\)** を検索します。

4. サブスクライブして、アプリをインストールします。

アプリをインストールしたので、組織で容量に関するメトリックを確認できるようになりました。 利用できる主要なメトリックをいくつか見てみましょう。

## <a name="use-the-metrics-app"></a>メトリックのアプリを使用する 
アプリを開くと、管理者権限があるすべての容量の概要を含むダッシュボードが最初に表示されます。

![Premium レポートの概要](media/service-admin-premium-monitor-capacity/app-dashboard.png)

### <a name="filtering"></a>フィルター処理

**[Filters applied to all pages]\(すべてのページに適用するフィルター\)** タブを使用すると、容量、データセット、過去 7 日間内の日付範囲を選択できます。 これらのフィルターの選択範囲は、このレポート内のすべての関連するページとタイルに適用されます。 何も選択しない場合、レポートは既定で、自分が所有するすべての容量の過去 1 週間のメトリックを表示します。

![Premium レポートの概要](media/service-admin-premium-monitor-capacity/premium-report-overview.png)

### <a name="summary-tab"></a>概要タブ

**[概要]** タブには、エンティティ、システム、データセットに基づく容量のビューが表示されます。

![すべてのページに適用されるフィルター](media/service-admin-premium-monitor-capacity/premium-summary-report.png)

| **領域** | **メトリック** |
| --- | --- |
| **エンティティ** | * 自分が所有する容量の数<br> * 容量内の個別データセットの数<br> * 容量内の個別ワークスペースの数 |
| **システム** | * 過去 7 日間の平均メモリ使用量 (GB)<br> * 過去 7 日間の最高メモリ消費量 (GB) およびそれが発生したローカル時刻<br> * 過去 7 日間で CPU がしきい値の 80% を超えた回数 (3 分間のバケットに分割)<br> * 過去 7 日間で CPU が 80% を超えた最大回数 (1 時間のバケットに分割) およびそれが発生したローカル時刻<br> * 過去 7 日間で直接クエリ/ライブ接続がしきい値の 80% を超えた回数 (3 分間のバケットに分割)<br> * 過去 7 日間で直接クエリ/ライブ接続が 80% を超えた最大回数 (1 時間のバケットに分割) およびそれが発生したローカル時刻 |
| **データセットのワークロード** | * 過去 7 日間の更新の合計数<br> * 過去 7 日間の成功した更新の合計数<br> * 過去 7 日間の失敗した更新の合計数<br> * メモリ不足によって失敗した更新の合計数<br> * 平均更新時間は分単位で測定されます (操作完了にかかった時間)<br> * 更新の平均待機時間は分単位で測定されます (スケジュールされた時間と操作の開始の間の平均ラグ)<br> * 過去 7 日間のクエリ実行の合計数<br> * 過去 7 日間の成功したクエリの合計数<br> * 過去 7 日間の失敗したクエリの合計数<br> * 平均クエリ時間は分単位で測定されます (操作完了にかかった時間)<br> * メモリ不足により解放されたモデルの合計数 |
|  |  |

### <a name="refreshes-tab"></a>更新タブ

**[Refreshes]\(更新\)** タブでは、完全な更新、成功したメジャー、過去 7 日間のデータセットで分割した更新待機時間の平均値/最大値と更新時間の平均値/最大値が一覧表示されます。 下部にある 2 つのグラフでは、更新とメモリ消費量 (GB)、および 1 時間のバケットに分割された平均待機時間 (ローカル時刻でのレポート) が表示されます。 上部の棒グラフでは、データセットの更新を完了するのにかかった最大時間 (更新時間) と更新の最大待機時間の合計による、上位 5 つのデータセットが一覧表示されます。 複数の更新待機時間の急増は、容量に波があることを示しています。

![Premium 更新レポート](media/service-admin-premium-monitor-capacity/premium-refresh-report.png)

### <a name="datasets-tab"></a>データセット タブ

**[データセット]** タブには、時間単位でメモリ不足によって解放された完全なデータセットが表示されます。

![Premium データセット レポート](media/service-admin-premium-monitor-capacity/premium-datasets-report.png)

### <a name="system-tab"></a>システム タブ

**[システム]** タブには、CPU の高使用率 (使用率が 80% を超えた回数)、直接クエリ/ライブ接続の高使用率、メモリ消費量が表示されます。

![Premium システム レポート](media/service-admin-premium-monitor-capacity/premium-system-report.png)

## <a name="monitor-power-bi-embedded-capacity"></a>Power BI Embedded 容量を監視する

Power BI Premium 容量メトリック アプリを使用して、Power BI Embedded の *A SKU* 容量を監視することもできます。 これらの容量は、容量の管理者であればレポートに表示されます。 ただし、A SKU で Power BI に特定のアクセス許可を付与しない限り、レポートの更新は失敗します。

1. Azure Portal で容量を開きます。
1. **[アクセス制御 (IAM)]** をクリックして、リーダー ロールに "Power BI Premium" を追加します。 名前でアプリを検索できない場合は、クライアント ID (cb4dc29f-0bf4-402a-8b30-7511498ed654) で追加することもできます。

    ![Power BI Embedded のアクセス許可](media/service-admin-premium-monitor-capacity/embedded-permissions.png)

> [!NOTE]
> アプリまたは Azure Portal でPower BI Embedded 容量使用率を監視することができますが、Power BI 管理ポータルではできません。

## <a name="basic-monitoring-in-the-admin-portal"></a>管理ポータルでの基本的な監視

管理者ポータルの **[容量の設定]** 領域では、容量によって過去 7 日間に置かれた負荷と使用されたリソースを示す、4 つのゲージが表示されます。 これら 4 つのタイルは 1 時間単位の時間枠に基づき、過去 7 日間で対応するメトリックが何時間 80% を超えたかを示します。 このメトリックは、エンドユーザーのエクスペリエンスが低下する可能性を示します。

![7 日間での使用状況](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **メトリック** | **説明** |
| --- | --- |
| CPU |CPU 使用率が 80% を超えた回数です。 |
| メモリ スラッシング |バックエンド コアのメモリ負荷を表します。 具体的には、これは、複数のデータセットの使用によるメモリ負荷により、データセットがメモリから締め出された回数のメトリックです。 |
| メモリ使用量 |平均メモリ使用量です (ギガバイト (GB) 単位)。 |
| DQ/秒 | 直接クエリとライブ接続の数が上限の 80% を超えた回数です。 <br> * DirectQuery の合計数と 1 秒あたりのライブ接続クエリの数を制限しています。* 制限は、P1 で 30/秒、P2 で 60/秒、 P3 で 120/秒です。 * 直接クエリとライブ接続クエリの数は、上記のスロットルに追加されます。 たとえば、15 の DirectQueries と 1 秒あたり 15 のライブ接続がある場合、スロットルに達しています<br>* これはオンプレミスおよびクラウドの接続にも等しく適用されます。 |
|  |  |

メトリックは、過去 1 週間の使用状況を反映します。  メトリックをさらに詳細に見たい場合は、概要タイルのいずれかをクリックします。  Premium 容量の各メトリックの詳細グラフが表示されます。 CPU のメトリックの詳細を次の図に示します。

![CPU の詳細使用状況グラフ](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

これらのグラフは、過去 1 週間について 1 時間ごとに集計され、Premium 容量で特定のパフォーマンス関連イベントが発生した可能性があるときを特定するのに役立ちます。

いずれかのメトリックの基になっているデータを、csv ファイルにエクスポートすることもできます。  エクスポートすると、過去 1 週間の詳細情報を 3 分間隔で見ることができます。

## <a name="next-steps"></a>次の手順

Power BI Premium 容量を監視する方法について学習したので、容量の最適化について学習します。

> [!div class="nextstepaction"]
> [Power BI Premium 容量のリソースの管理と最適化](service-premium-understand-how-it-works.md)
