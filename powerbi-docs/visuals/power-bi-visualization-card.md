---
title: 'カード視覚エフェクト (別名: 大きな数字のタイル)'
description: Power BI でカード視覚エフェクトを作成します
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 03/26/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 18c9fe3d50245ff1d0745c0a3ae1e830b3f9be45
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2018
ms.locfileid: "46548329"
---
# <a name="card-visualizations"></a>カード視覚エフェクト
Power BI のダッシュボードまたはレポートで追跡すべき最重要の項目が 1 つの数値だけという場合もあります。たとえば、総売上高、対前年比の市場シェア、営業案件の総数などがこれに該当します。 この種の視覚エフェクトは、"*カード*" と呼ばれます。 他のほとんどのネイティブな Power BI 視覚エフェクトと同様に、カードもレポート エディターまたは Q&A を使って作成できます。

![カード視覚エフェクト](./media/power-bi-visualization-card/pbi_opptuntiescard.png)

## <a name="create-a-card-using-the-report-editor"></a>レポート エディターを使ってカードを作成する
次の手順では、「Retail Analysis Sample」を使用します。 作業を進めるために、Power BI サービス (app.powerbi.com) または Power BI Desktop の[サンプルをダウンロード](../sample-datasets.md)します。   

1. [空のレポート ページ](../power-bi-report-add-page.md)を開始し、**[Store]** \> **[Open store count]** フィールドを選びます。 Power BI サービスを使っている場合は、[編集ビュー](../service-interact-with-a-report-in-editing-view.md)でレポートを開く必要があります。

    Power BI によって、1 つの数値のみが含まれた縦棒グラフが作成されます。

   ![](media/power-bi-visualization-card/pbi_rptnumbertilechart.png)
2. [視覚化] ウィンドウで [カード] アイコンを選びます。

   ![](media/power-bi-visualization-card/pbi_changechartcard.png)
6. カードをポイントし、ピン留めアイコン ![](media/power-bi-visualization-card/pbi_pintile.png) を選んで、ダッシュボードに視覚エフェクトを追加します。

   ![](media/power-bi-visualization-card/power-bi-pin-icon.png)
7. タイルを既存のダッシュボードまたは新しいダッシュボードにピン留めします。

   * 既存のダッシュボード: ドロップダウンから、ダッシュボードの名前を選びます。
   * 新しいダッシュボード: 新しいダッシュボードの名前を入力します。
8. **[Pin]**(ピン留め) を選択します。

   右上隅の近くに成功メッセージが表示されたら、視覚エフェクトがダッシュボードにタイルとして追加されたことがわかります。

   ![](media/power-bi-visualization-card/power-bi-pin-success-message.png)
9. **[ダッシュボードへ移動]** を選びます。 ピン留めされた視覚化の[編集と移動](../service-dashboard-edit-tile.md)をそこで行うことができます。


## <a name="create-a-card-from-the-qa-question-box"></a>Q&A 質問ボックスからカードを作成する
Q&A の質問ボックスは、カードを作成する最も簡単な方法です。 Q&A 質問ボックスは、Power BI サービス (app.powerbi.com) のダッシュボードまたはレポートから利用できます。 以下の手順では、Power BI サービスのダッシュボードからカードを作成する方法について説明します。 Power BI Desktop で Q&A を使ってカードを作成したい場合は、Desktop レポートの Q&A プレビューに関する[こちらの手順に従って](https://powerbi.microsoft.com/en-us/blog/power-bi-desktop-december-feature-summary/#QandA)ください。

1. [ダッシュボード](../consumer/end-user-dashboards.md)を作成して、[データを取得](../service-get-data.md)します。 この例では、[営業案件の分析のサンプル](../sample-opportunity-analysis.md)を使います。

1. ダッシュボードの上部にある質問ボックスに、データに関する質問を入力します。 

   ![](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

>**ヒント**: Power BI サービスのレポートの場合は、[編集ビュー](../consumer/end-user-reading-view.md)の上部メニュー バーから **[質問する]** を選びます。 Power BI Desktop のレポートの場合は、レポートの空いている領域をダブルクリックして質問ボックスを開きます。

3. たとえば、質問ボックスに「number of opportunities」(営業案件の数) と入力します。

   ![](media/power-bi-visualization-card/power-bi-q-and-a.png)

   質問ボックスでは、役立つ提案や説明が示された後、最終的に合計数が表示されます。  
4. 右上隅にあるピン留めアイコン ![](media/power-bi-visualization-card/pbi_pintile.png) を選んで、カードをダッシュボードに追加します。

   ![](media/power-bi-visualization-card/power-bi-pin.png)
5. 既存のダッシュボードまたは新しいダッシュボードに、カードをタイルとしてピン留めします。

   * 既存のダッシュボード: ドロップダウンから、ダッシュボードの名前を選びます。 現在のワークスペース内のダッシュボードのみを選択できます。
   * 新しいダッシュボード: 新しいダッシュボードの名前を入力すると、現在のワークスペースに追加されます。
6. **[Pin]**(ピン留め) を選択します。

   右上隅の近くに成功メッセージが表示されたら、視覚エフェクトがダッシュボードにタイルとして追加されたことがわかります。  

   ![](media/power-bi-visualization-card/power-bi-success.png)
7. **[ダッシュボードへ移動]** を選択して新しいタイルを表示します。 ここでは、ダッシュボード上のタイルに対して、[名前の変更、サイズ変更、ハイパーリンクの追加、位置変更など](../service-dashboard-edit-tile.md)を行うことができます。

   ![](media/power-bi-visualization-card/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
- 質問ボックスがまったく表示されない場合は、システム管理者またはテナント管理者に問い合わせてください。    
- Desktop を使っていて、レポートの空き領域をダブルクリックしても Q&A が開かない場合は、Q&A を有効にする必要がある場合があります。  **[ファイル] > [オプションと設定] > [オプション] > [プレビュー機能] > [Q&A]** の順に選んでから、Desktop を再起動します。

## <a name="format-a-card"></a>カードの書式設定
ラベル、テキスト、色などを変更するオプションは多数あります。 最善の学習方法は、カードを作成し、[書式設定] ウィンドウを探索することです。 利用可能な書式設定オプションのほんの一部を次に示します。 

1. 最初にペイントブラシのアイコンを選んで、[書式設定] ウィンドウを開きます。 

    ![](media/power-bi-visualization-card/power-bi-format-card.png)
2. **[データ ラベル]** を展開し、色、サイズ、フォント ファミリを変更します。 数千の店舗がある場合は、**[表示単位]** を使用して、店舗の数を千単位で表示でき、小数点以下の桁数も制御できます。 たとえば、125,832.00 ではなく 125.8 K のようになります。

3.  **[カテゴリ ラベル]** を展開し、色とサイズを変更します。

    ![](media/power-bi-visualization-card/power-bi-card-format.png)

4. **[背景]** を展開し、スライダーを [オン] に移動します。  これで、背景色と透明度を変更できます。

    ![](media/power-bi-visualization-card/power-bi-format-color.png)

5. カードが希望どおりになるまで書式設定オプションの探索を続けます。 

    ![](media/power-bi-visualization-card/power-bi-formatted.png)

## <a name="next-steps"></a>次の手順
[Power BI のダッシュボードのタイル](../consumer/end-user-tiles.md)

[Power BI のダッシュボード](../consumer/end-user-dashboards.md)

[Power BI - 基本的な概念](../consumer/end-user-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。
