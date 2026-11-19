### Graph
uv run python -m app.agent --graph --trace "$AIE_QUESTION"
[model] gemini-3.5-flash-lite
第2回の講義資料によると、LoRAとQLoRAの仕組みについて以下のように説明されています。

* **LoRAが固定するものと学習するもの**
  * **固定するもの**：モデルの元の重み（本体）は固定し、学習しません（第2回・PDF p.52）。
  * **学習するもの**：変化分を表す細長い2つの小さな行列（低ランク行列 $\text{A}$・$\text{B}$）の差分だけを学習します（第2回・PDF p.51, 52）。

* **QLoRAが加えるもの**
  * LoRAの手法に加えて、**元の重みを4bitに圧縮（量子化）**すること加えます（第2回・PDF p.51, 52）。これにより、大きなモデルでもより少ないGPUメモリ（GPU1台など）で調整できるようになります（第2回・PDF p.52）。

--- trace ---
[tool call]   search_graph({'query': 'LoRA 固定 学習 QLoRA 追加'})
[tool return] search_graph -> {"seeds": [{"page_id": "lec02-main-p052", "document_id": "lec02-main", "lecture": 2, "document_title": "基盤モデルの仕組み", "sec…
[time] 回答完了まで 14.62 秒（検索・埋め込みを含む）
[usage] 入力 5,775 tokens / 出力 228 tokens / モデル応答 2 回
[cost] 生成APIの推定コスト: $0.002302 USD（埋め込み・索引構築分は含まない）