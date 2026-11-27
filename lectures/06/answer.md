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
- やったこと：`app/mcp_server.py` に `server.tool()(tools.get_lecture_summary)` を1行追加し、MCPサーバーで公開するツールを増やした。
- 結果：
 - `uv run python -m app.mcp_agent --list-tools` を実行し、`glossary_get_lecture_summary` が一覧に追加されたことを確認した。
 - `uv run python -m app.mcp_agent --trace "第2回では何を学びますか？"` を実行し、追加したツールが呼び出されて第2回の要点が正しく返ってくることを確認した。
 - `uv run pytest -q` を実行し、21 passed となりすべてのテストが通ることを確認した。
- 気づき・疑問：エージェント本体（`app/mcp_agent.py`）や設定ファイル（`app/mcp_servers.json`）を一切書き換えなくても、MCPサーバー側でツールを追加して公開するだけで、エージェント起動時に自動でツール一覧を取得して使えるようになる点が便利だと感じた。
