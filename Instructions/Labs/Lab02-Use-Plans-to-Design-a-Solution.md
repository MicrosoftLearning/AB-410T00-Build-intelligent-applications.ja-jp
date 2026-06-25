---
lab:
  title: AI 搭載の Plans を使って Contoso Field Services ソリューションを設計します
  description: Microsoft Power Apps の Plans を使用して、ビジネス ニーズを構造化されたソリューション ブループリントに変換する
  duration: 30 minutes
  level: 200
  islab: true
---

# AI 搭載の Plans を使って Contoso Field Services ソリューションを設計します

この演習では、Microsoft Power Apps の AI 搭載の Plans を使用して、Contoso のビジネス上の課題を説明し、構造化されたソリューション ブループリントを生成し、この後の演習で構築するデータ モデル、アプリ、自動化を特定します。

この演習の所要時間は約 **30** 分です。

## シナリオ

Contoso Field Services は、機器の故障を報告する顧客からのサービス要求を管理するための一元化されたソリューションを必要としています。 今日、要求は電話とメールで届き、スプレッドシートで手動で追跡しています。 技術者は、割り当てられているジョブを常に把握しているわけではありません。顧客は要求の状態を確認する方法がなく、マネージャーはエスカレーションの優先順位付けに苦労しています。

あなたは、これらの問題に対処する AI ファーストの Power Platform ソリューションの設計を依頼されました。 ゼロから設計するのではなく、AI 搭載の Plans を使ってビジネス ニーズを説明し、AI がソリューション ブループリントを生成します。

## タスク 1: ビジネス上の問題を Plans に説明する

1. [**Power Apps**](https://make.powerapps.com) (`https://make.powerapps.com`) を開き、Microsoft アカウントでサインインします。

1. 正しい環境にいることを確認します。 右上隅にある環境ピッカーを選択し、トレーニング環境を確認または選択します。

1. 左側のナビゲーションで **[Plans]** を選択します。 

1. **[プランの作成]** を選択します。

1. 説明ボックスに、ビジネス問題を次のように入力します。

    ```
    Contoso Field Services needs to manage service requests from business customers whose industrial equipment has failed. When a customer reports an issue, a service request should be created. Service requests should have a priority field — Low, Normal, High, and Critical. A service manager needs to view and prioritize all open requests and assign a technician. Requests marked Critical should automatically trigger a manager approval before a technician is assigned. The assigned technician needs a mobile app to view their jobs and update the status. Customers should be able to submit new requests and check the status of existing ones online. When a request is submitted, the assigned technician should receive a notification automatically.
    ```

1. **[生成]** を選択し (または **Enter** キー押して)、Plans で説明が処理されるまで待ちます。

## タスク 2: 生成されたソリューション ブループリントを確認する

1. **[要件]** を確認します。 要件エージェントが、あなたの説明から解釈したビジネスの問題を要約します。 サービス要求管理、技術者割り当て、顧客ポータル、通知、重要な要求の承認など、主要なニーズが確実に取り込まれていることを確認します。

1. 内容に問題がなければ、**[問題ありません]** を選択します。 プロセス エージェントがプロセスを生成します。

1. **[プロセス]** セクションを確認します。 プロセス エージェントにより、サービス要求の送信、技術者の割り当て、重要な要求承認のルーティングなど、特定された主要なビジネス プロセスが表示されます。 あなたの説明のメイン ワークフローが反映されていることを確認します。 **[プロセスの表示]** を選択すると、ビジネス プロセスの分岐フロー チャートを表示できます。

1. 内容に問題がなければ、**[問題ありません]** を選択します。

1. **[データ]** セクションを確認します。 Plans で提案されたテーブル (例: サービス要求、顧客、技術者) に注目します。 問題がなければ、**[問題ありません]** を選択します。

1. **[テクノロジー]** セクションを確認します。 ここにはアプリ、オートメーション、ページが 1 つのビューにまとめられています。 技術者向けのキャンバス アプリ、マネージャー向けのモデル駆動型アプリ、通知と承認のためのフロー、外部顧客向けの Power Pages サイトへの参照が表示されていることを確認します。 問題がなければ、**[問題ありません]** を選択します。

   > [!NOTE] 
   > Plans は、あなたの説明を使用してソリューション コンポーネントを提案します (正確な出力は異なる可能性があります)。 データ → アプリ → オートメーション → ポータル、というソリューションの全体的な形が重要です。 これはラボ 3 からラボ 10 を通して構築されるのと同じ構造です。

## タスク 3: ブループリントをビルド ガイドとして確認する

少し時間をかけて、ブループリント全体を確認し、今後の演習と関連付けてみてください。

1. Plans で推奨された**テーブルと列**を特定します。これらはラボ 3 で作成します。

1. フィールド技術者向けの**キャンバス アプリ**を特定します。これは、ラボ 5 で構築します。

1. サービス マネージャー向けの**モデル駆動型アプリ**を特定します。これは、ラボ 6 で構築します。

1. **顧客ポータル**を特定します。これは、ラボ 7 で作成します。

1. 技術者への通知用の**自動フロー**を特定します。これはラボ 8 で構築します。

1. 重要な要求の **承認フロー**を特定します。ラボ 9 で構築します。

1. Dataverse データからの AI 生成による応答から、エージェントにもたらされる付加価値に注目します。ラボ 10 でこれを構築します。

   > [!NOTE] 
   > ここでは、これらのテーブルやオブジェクトを基に構築はしません。 Plans は設計ツールであり、"何を" 構築するのか、その "理由" を理解するのに役立ちました。**** このほかのラボでは、各コンポーネントを自分で一から構築するので、その仕組みを正確に理解できます。 まず、ラボ 3 で新しいソリューションを作成するところから始めます。
