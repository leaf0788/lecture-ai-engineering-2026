# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：
- STEP 2 の [tool call]：
- STEP 3 の [tool call]：
- STEP 4 の [tool call]：
- 気づき・疑問：

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎

- やったこと：
`app/mcp_server.py` に `server.tool()(tools.get_lecture_summary)` を追加し、MCPサーバーから `get_lecture_summary` を公開した。

- 結果：
`uv run python -m app.mcp_agent --list-tools` を実行し、`glossary_get_lecture_summary` がツール一覧に追加されたことを確認した。

さらに「第2回では何を学びますか？」と質問したところ、`[tool call] glossary_get_lecture_summary({'lecture': 2})` と表示され、追加したツールが実際に呼び出された。

`uv run pytest -q` では `21 passed` となり、すべてのテストが成功した。

- 気づき・疑問：
エージェント側のコードを変更しなくても、MCPサーバー側でツールを公開するだけで新しい機能を利用できることが確認できた。起動時にサーバーから利用可能なツール一覧を取得する仕組みにより、機能を柔軟に追加できる点が印象に残った。