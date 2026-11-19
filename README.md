# 社會心理學 LLM Wiki：團體歷程與社會影響

本資料夾是既有社會心理學 GitHub Wiki 的主題擴充包，包含五份 Markdown 知識來源、ingestion manifest 與瀏覽器端 retrieval 測試頁。

## 檔案結構

- `sources/S01_group_basics.md`：團體基本概念
- `sources/S02_individual_behavior.md`：團體中的個人行為
- `sources/S03_group_decisions.md`：團體決策與團體問題
- `sources/S04_conflict_cooperation.md`：衝突與合作
- `sources/S05_social_influence_leadership.md`：社會影響與領導
- `ingest-manifest.json`：來源清單與 metadata
- `retrieval.html`：GitHub Pages 可執行的檢索測試介面
- `workflow-log-template.md`：實際測試與反思紀錄表

## GitHub 部署

將本資料夾內的內容（不是外層資料夾）上傳至既有 Repository 根目錄，或放入 Repository 的 `llm-wiki-group-processes/` 子資料夾。

若放在根目錄，檢索頁網址為：
`https://<username>.github.io/<repository>/retrieval.html`

若放在子資料夾，網址為：
`https://<username>.github.io/<repository>/llm-wiki-group-processes/retrieval.html`

## 目前 ingestion / retrieval 的真實範圍

1. 五份 Markdown 是五個知識來源單位，已整理成具 metadata 的文件。
2. `ingest-manifest.json` 記錄來源 ID、章節、主題、檔案路徑及核對狀態。
3. `retrieval.html` 透過 `fetch()` 讀取 manifest 與 Markdown 文件，並以關鍵詞重疊排序相關片段。
4. 這是可部署於 GitHub Pages 的靜態檢索原型，**不是向量資料庫，也不是完整 LLM RAG**。目前沒有 embeddings、向量資料庫或 LLM API 呼叫。
5. 不可將任何 API 金鑰放在公開前端程式碼。

## 資料可信度

目前定義是依先前對話中已整理的課程圖片轉錄；因無法將每一段定義精確對應至原圖頁碼，文件皆標記 `needs-verification`。特別是 S02 的「社會性懈怠」定義，先前已指出可能與常見教材敘述不一致，必須回看原圖核對後才可用於正式教學簡報。

五份文件是本次主題知識單位，不等於五篇外部學術論文。若老師所說的「5 篇資料」限定為五份原始文獻或五份獨立教材，仍需依原始來源實際檔案重新計數與標記。

## 下一步

- 將原始圖片逐張對應到各名詞，補上檔名與頁碼。
- 核對 S02 社會性懈怠及 S01 交換記憶等待確認內容。
- 在 GitHub Pages 部署後執行五個 retrieval 測試問題。
- 將實際結果填入 `workflow-log-template.md`。
- 再把通過核對的知識片段提供給 LLM 生成教學 HTML 簡報。
