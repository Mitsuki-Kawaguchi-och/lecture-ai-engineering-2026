# 第1回 解答

## 演習

- 講座に固有の質問（宿題の3レベル）へのモデルの回答（要約でよい）：  
「Low-Rank Adaptation（低ランク適応）」の略で、AI（特に大規模言語モデルや画像生成AI）の**ファインチューニング（追加学習）を効率よく行うための技術**。  
LoRAは、AIの本体（ベースモデル）の重み係数は**完全固定**し、その横に**「ごくわずかな追加のパラメータ（LoRAモジュール）」**だけを接続してそこだけを学習するため、  
**「誰でも手軽に、低コストでAIを自分好みにカスタマイズできるようにした技術」**となる。

- 用語集の正しい意味と比べて気づいたこと：  
AIの出力はPEFTのような用語を一部使わずに、概念を例示を用いたり、平易な言葉を使用したりして説明している。

- 表示できたトークン数（入力 / 出力）：  
[入力トークン数] 7  
[出力トークン数] 620


## 宿題

- 取り組んだレベル：基礎

- やったこと：gemini-3.5-flash-lite/gemini-3.6-flash/gemini-3.8-flashでLoRAに対する回答比較、temperatureの指定

- 結果：
    - 生成時間（生成の速さ）  
    　gemini-3.5-flash-lite＞gemini-3.6-flash＞gemini-3.8-flash
    - 生成内容（具体例、時系列などが充足しているか）  
    　gemini-3.5-flash-lite＜gemini-3.6-flash＜gemini-3.8-flash
    - temperatureの指定  
     ```TypeError: Models.generate_content() got an unexpected keyword argument 'temperature'```  
     上記のようになり指定不可

- 気づき・疑問：  
gemini-3.5-flash-lite/gemini-3.6-flash/gemini-3.8-flashの3モデルでは、今回のLoRAに対する質問内容だとあまり差がないと感じた。  
より曖昧な質問内容ではどこまで差がでるか気になったため、これからの演習でモデルごとの特徴を掴みたい。
