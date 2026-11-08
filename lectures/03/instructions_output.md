### 変更内容（INSTRUCTIONS）
INSTRUCTIONS = """\
あなたはAIエンジニアリング講座（AIE2026）の学習支援エージェントです。
- 用語や講座に固有のことを答える前に、必ず search_glossary で用語集を確認する。
- 回の内容を聞かれたら get_lecture_summary を使う。
- 用語集に見つからないことは、推測で断定せず「用語集にはない」と伝える。
- 回答の最後に、関係する回（第N回）を示す。
- 関係する回の要点を必ず示す。必ず get_lecture_summary を使う。
- 宿題の答えそのものは書かず、考え方のヒントで導く。
"""

### 出力内容
uv run python -m app.agent --trace " 第2回の内容から確認問題を 1問出して" 
[model] gemini-3.5-flash-lite
第2回の内容から、LoRAに関する確認問題です！

**【問題】**
「LoRA」とはどのような手法でしょうか？

---

（関連する回：第2回 ファインチューニングとLoRA）

**■ 第2回の要点**
- **事前学習とファインチューニング**：汎用モデルを目的のデータで追加学習させ、出力形式や口調などを調整する。
- **PEFTとLoRA**：全パラメータを更新せず、小さな低ランク行列だけを学習することで、メモリや保存容量を大幅に削減する。
- **演習のポイント**：Qwen3.5-0.8Bなどの小さなモデルを用いて、架空FAQデータをもとにLoRA学習を行い、学習前後でモデルの振る舞いがどう変わるかを体験する。

--- trace ---
[tool call]   make_quiz({'lecture': 2})
[tool return] make_quiz -> 問題:「LoRA」の意味は？
答え: 事前学習済みの重みは固定したまま、重みの更新分を2つの小さな行列の積（低ランク行列）で表し、その小さな行列だけを学習するPEFT手法。学習するパラメータが少なく、学習結果（アダプタ）も小さいファイルで保…
[tool call]   get_lecture_summary({'lecture': 2})
[tool return] get_lecture_summary -> # 第2回 ファインチューニングとLoRA

## この回のねらい

- 事前学習とファインチューニングの違い、ファインチューニングが向く場面と向かない場面を理解する
- LoRAの考え方を理解し、Google Colab上で小さなモデルを…
[usage] RunUsage(cost=Decimal('0.0011183'), details={'text_prompt_tokens': 2011}, input_text_tokens=2011, input_tokens=2011, output_tokens=206, requests=3, tool_calls=2)