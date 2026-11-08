### tools
uv run python -m app.agent --list-tools
モデルに見えているツール: 3 個

[search_glossary]
  講座の用語集から用語を検索し、定義と、どの回で扱うかを返す。
  
  AIエンジニアリングの用語や、この講座（AIE2026）に固有の言葉について
  答える前に使うこと。query には調べたい用語を1つだけ入れる（例: "LoRA"）。
  引数: {"query": {"type": "string"}}

[get_lecture_summary]
  指定した回（1始まりの整数）の講義の要点を返す。
  
  「第3回では何を学ぶ？」のように、回の内容や関係を聞かれたときに使う。
  引数: {"lecture": {"type": "integer"}}

[make_quiz]
  指定した回の用語について小テストを作るときに使う。
  
  用語集からその回の用語を1つ選び、「用語の意味は？」という問題と定義を返す。
  引数: {"lecture": {"type": "integer"}}

---
### trace
uv run python -m app.agent --trace " 第2回の内容から確認問題を 1問出して" 
[model] gemini-3.5-flash-lite
第2回の内容から確認問題を出します！

**【問題】**
「ランク（LoRAの $r$）」とは何でしょう？

**【答えのヒント】**
LoRAでモデルの重みを効率よく調整するために導入される、低ランク行列の大きさを決めるハイパーパラメータです。この値が大きくなるとどうなるか、表現力やメモリの観点から考えてみてくださいね！

（関連：第2回）

--- trace ---
[tool call]   make_quiz({'lecture': 2})
[tool return] make_quiz -> 問題:「ランク（LoRAのr）」の意味は？
答え: LoRAで使う低ランク行列の大きさを決めるハイパーパラメータ。大きいほど表現力が上がるが、学習するパラメータとメモリも増える。…
[usage] RunUsage(cost=Decimal('0.0005408'), details={'text_prompt_tokens': 861}, input_text_tokens=861, input_tokens=861, output_tokens=113, requests=2, tool_calls=1)