### STEP 3：検索結果を使って回答させる
uv run python -m app.agent --trace "$AIE_QUESTION"
[model] gemini-3.5-flash-lite
第2回の講義資料によると、LoRAとQLoRAの仕組みについて以下のように説明されています。

* **LoRAが固定するもの・学習するもの**
  * **固定するもの**：元の重み $W$（学習せず、そのままにする）
  * **学習するもの**：細長い2つの小さな行列（行列 $A$ と $B$）の積で表される変化分（差分）だけを学習する
  （第2回・PDF p.51, p.52）

* **QLoRAが加えるもの**
  * LoRAの仕組みに加え、**元の重みを4bitに圧縮（量子化）**することを加えます。
  （第2回・PDF p.51, p.52）

--- trace ---
[tool call]   search_materials({'query': 'LoRA QLoRA 固定 学習'})
[tool return] search_materials -> {"results": [{"page_id": "lec02-main-p052", "document_id": "lec02-main", "lecture": 2, "document_title": "基盤モデルの仕組み", "s…
[time] 回答完了まで 35.60 秒（検索・埋め込みを含む）
[usage] 入力 3,539 tokens / 出力 189 tokens / モデル応答 2 回
[cost] 生成APIの推定コスト: $0.001534 USD（埋め込み・索引構築分は含まない）