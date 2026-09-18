# talk

**Talk = 会話そのものではなく、関心と状態を動かすプロセス。**

## 前提

Talkは発話の集合ではない。

相手に関心があれば続き、関心がなくなれば終わる。

```
関心
 ↓
Talk
 ↓
関心が増える / 維持される / なくなる
 ↓
Continue / End
```

**DecisionはTalkではない。**  
認識・感情・関係・関心が変化した結果、主体の心の中で決まり、その後にActionが起きる。

## Talkの7タイプ

目的に基づく共通語彙。

1. **Know** — 知る
2. **Connect** — つながる
3. **Enjoy** — 楽しむ
4. **Explore** — 広げる
5. **Understand** — 腑に落ちる
6. **Feel** — 感じる
7. **Continue** — 続ける

**Endは8番目のTalkではない。**  
関心が失われた結果として会話が終わる。

## Talk Model

```yaml
Talk:
  actor: Agent
  partner: Agent
  domain: Domain
  context: Context
  purpose: Purpose
  type: TalkType
  topic: Topic
  action: TalkAction
  ask: Ask
  reaction: Reaction
  interest: Interest
  state: State
  outcome: Outcome
```

## Ask

**Ask = 次のTalkを選ぶための選択。**

```
current state
+
current interest
+
domain knowledge
+
conversation memory
↓
Ask
↓
Talk
↓
Reaction
↓
interest / state update
```

## Domain

Talk自体はドメイン非依存。

Domainごとに前提知識と事例を持つ。

```
Domain
├── knowledge
├── corpus
└── cases
      ↓
     RAG
      ↓
Domain Context
      ↓
     Talk
```

対象例:

- idol
- cabaret
- host
- fashion-sales
- insurance-sales
- uber-driver-recruitment
- pickup
- judge

## AW

**AW = DomainごとのTalk事例を収集し、知識へ育てる仕組み。**

成功事例だけではなく、

```
関心増加
関心維持
関心低下
会話終了
拒否
```

を含めて収集する。

事例は、

```
Before
  ↓
Talk
  ↓
Reaction
  ↓
After
```

として記録し、RAGで再利用する。

## Core Principle

**Talkは「何を言うか」ではなく、「相手の関心と状態がどう変化するか」を扱う。**

Domainが変わっても、Talkのモデルは変わらない。
