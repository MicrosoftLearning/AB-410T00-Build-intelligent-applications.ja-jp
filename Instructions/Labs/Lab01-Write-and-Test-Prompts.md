---
lab:
  title: Contoso Field Services のためのプロンプトを書いてテストする
  description: Contoso のサービス エージェントをサポートする生成 AI ツール用の、効果的なプロンプトを書いて洗練させる練習をする
  duration: 15 minutes
  level: 200
  islab: true
---

# Contoso Field Services のためのプロンプトを書いてテストする

この演習では、プロンプト エンジニアリングの手法の練習として、プロンプトを書いて洗練させます。この目的は Contoso Field Services のエージェントが顧客の問い合わせに速く応答できるようにするとともに、応答に一貫性を持たせることです。

この演習の所要時間は約 **15** 分です。

## シナリオ

Contoso Field Services は産業用機器の設置と修理を行う会社であり、地域全域の企業を顧客としています。 サービス チームは毎日数十件もの顧客からの電話に対応しており、要求の状態、トラブルシューティングの手順案内、技術者が来るのを待つ間の次のステップなどの質問に答えています。

現時点では、エージェントはこのような質問に対して手作業でドキュメントや過去の事例を調べて回答しています。 あなたの任務は、生成 AI を使うエージェントのためにプロンプトを書くことであり、そのねらいは正確でプロフェッショナルにふさわしい、役立つ回答を即座に生成できるようにすることです。

## タスク 1: 基本的なプロンプトを書く

まず、シンプルなプロンプトを書き、具体性がどのように回答の質に影響するかを観察します。

1. [**Microsoft Copilot**](https://copilot.microsoft.com) (`https://copilot.microsoft.com`) を開いて自分の Microsoft アカウントでサインインします。

1. アカウントを選択する画面が表示された場合は、**職場**アカウントを選択します。

1. ようこそメッセージが表示された場合は、閉じてください。

1. チャット ボックスに次のプロンプトを入力して **Enter** キーを押します。

    `A customer's equipment isn't working. What should they do?`

1. 応答を確認します。 AI からの回答が普遍的であることに注目してください。会社や機器の種類について、あるいは誰からの質問かといったコンテキストがないからです。

1. 次に示す、具体性を高めたバージョンを入力します。

    `A Contoso Field Services customer's industrial pump has stopped working mid-shift. What immediate steps should a service agent tell the customer to take while waiting for a technician?`

1. 2 つの回答を比較します。 会社名、製品の種類、対象者 (サービス エージェント)、状況 (技術者が来るのを待っている) を追加した結果として、はるかに有用な回答が得られることに注目してください。

   > [!NOTE]
   > AI の応答の質は、プロンプトの質に直接左右されます。 具体性こそが、より良い出力への最短の近道です。

## タスク 2: ペルソナとコンテキストを設定する

次に、質問の前に AI の役割を定義して背景コンテキストを与えてみましょう。 これは "システム プロンプト" と呼ばれることもあります。**

1. Copilot で新しい会話を始めるために **[新しいチャット]** を選択します。

1. 次のプロンプトを入力します。これで、AI が誰であり、何を知っているかを明確にしたうえで質問することになります。

    ```
    You are a helpful support assistant for Contoso Field Services, a company that installs and repairs industrial equipment for business customers. You help service agents respond to customer inquiries in a professional, empathetic, and concise tone. Always encourage the customer to avoid operating affected equipment until a technician has assessed it, and confirm that Contoso will follow up within 4 business hours.

    A customer calls to say their conveyor belt system stopped working during a production shift. What should the agent say?
    ```

1. 応答を確認します。 ペルソナ指示の結果としてトーン、細部、締めくくりの言葉がどのように変化するかに注目してください。

1. 同じ会話の中でフォローアップの質問をします。ただし、ペルソナを繰り返すことはしません。

    `The customer says the system tripped a safety shutoff. What should the agent advise now?`

1. Copilot での会話が続く間、Contoso のコンテキストはあなたが改めて指示しなくても維持されていることに注目してください。

## タスク 3: 出力の形式を制約する

次に、応答の長さ、形式、対象者をどのようにコントロールするかを練習します。

1. 次のプロンプトを入力します。これで、出力についての具体的な制約が追加されます。

    ```
    You are a Contoso Field Services support assistant.

    A customer reports that their refrigeration unit is making unusual noises and the temperature inside is rising. Write a response the agent can send to the customer. The response must:
    - Be no longer than 3 sentences
    - Acknowledge the issue
    - Give one immediate action the customer can take
    - Confirm that a technician will follow up
    ```

1. 制約によって出力がどのように変化したかを確認します。

1. 応答を短いメッセージではなく**フォーマルなメール形式**で返すようにプロンプトを修正して、もう一度送信します。 出力がどのように変化するかを観察します。

1. もう一度プロンプトに修正を加えます。今度は、**技術者ではない顧客**が機器の専門用語に詳しくない場合でも理解できるように応答を書いてほしいと依頼します。

   > [!NOTE]
   > 制約を加える、つまり長さ、形式、トーン、対象者を指定すると、AI の出力が単に技術的に正しいだけでなく、実際の業務にそのまま使えるものにすることができます。

## タスク 4: フューショット例を使う

フューショット プロンプトとは、AI に対してあなたが望むスタイルや形式の例を示してから実際の質問をすることです。

1. 次のプロンプトを入力します。

    ```
    You are a Contoso Field Services support assistant. Use the examples below to guide your tone and format.

    Example 1:
    Customer: My air compressor keeps shutting off.
    Agent: Thank you for contacting Contoso Field Services. This can sometimes be caused by overheating. Please ensure the unit has adequate ventilation and check that the air filter is clean. A technician will follow up with you within 4 business hours.

    Example 2:
    Customer: The control panel on my equipment is showing an error code.
    Agent: Thank you for reaching out. Please note the error code displayed and avoid operating the equipment until our technician has assessed it. We will be in contact shortly to arrange a visit.

    Now respond to this inquiry:
    Customer: My hydraulic press is leaking fluid and I cannot stop production.
    ```

1. この応答のスタイルを、前に試したときのものと比較します。 例に従って、どのように形式と締めくくりの言葉が変化しているかに注目してください。

1. 最後の顧客メッセージを、あなたが選んだ別のシナリオに置き換えて、もう一度送信します。 AI がどのように同じスタイルを新しい状況にも適用しているかを観察します。

   > [!NOTE]
   > フューショット プロンプトが特に有益となるのは、多数のやり取り全体で出力に一貫性を持たせたいときです。たとえば、多数のエージェントに使用させる Copilot Studio トピックや AI Builder プロンプト アクションを構築するときです。

## まとめ

この演習では、プロンプト エンジニアリングの中核的な手法である次の 4 つを練習しました。

| 手法 | 実行内容 |
|-----------|-------------|
| **具体性** | 会社、製品、役割に関するコンテキストを加えると関連性が高まる |
| **ペルソナとコンテキスト** | システムレベルの指示によって会話全体での AI のトーンと挙動を設定する |
| **出力の制約** | 応答をそのまま利用できるように長さ、形式、対象者をコントロールする |
| **フューショット例** | 望ましいスタイルを実際に示すと、出力の一貫性が向上する |

これらと同じ手法が、Power Platform で作成するプロンプト (これには Copilot Studio のトピックや AI Builder のプロンプト アクションも含まれます) にも直接当てはまりますが、これらについてはこのコースで後ほど、別の演習で取り上げます。
