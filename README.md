# project-common

期中專題三個子組的**共用內容**。三組從這裡取得共同輸入，各自在自己的 repo 作業。

| Repo | 用途 |
| --- | --- |
| `project-common` | 共用輸入與共用規則（本 repo） |
| `group-waterfall` | Waterfall + AI 組 |
| `group-agile` | Agile + AI 組 |
| `group-AI` | AI-Agent 組 |

## 內容

| 檔案 | 說明 |
| --- | --- |
| `docs/VISION.md` | **起始文件**。三組唯一的共同輸入，定案後各組獨立做需求分析 |
| `docs/COMMIT_CONVENTION.md` | commit message 規則，三個 repo 共用 |
| `docs/AI_LOG_TEMPLATE.md` | AI 使用紀錄範本。各組複製到自己 repo 的 `docs/ai-log/` 填寫 |
| `.gitmessage` | commit 範本，跑 `git config commit.template .gitmessage` 後生效 |
| `.gitignore` | Godot 與 IDE 的忽略規則 |

## 規則重點

- `VISION.md` **只有這一份**。定案後要修改須經三組同意，並記在文件第 12 節。不要在各組 repo 內另存副本修改。
- 各組交付物為 **prototype 與相關文件**；prototype 完成即視為該組完成。
- 完成前不讀取其他組的 repo。
- **引擎版本三組必須一致**：Godot 4.7.2 / standard 版 / GDScript / Forward+，見 `VISION.md` 第 10 節。
- **AI 工具不統一**，各組自行選用，但須揭露工具版本、模型，以及啟用了哪些自動化。

## 待三組確認

`VISION.md` 中標為 **【提案，待三組確認】** 的項目尚未經三組同意，確認前各組以其為工作假設：

- 共用骨架的界線（只共用 `project.godot` 與 `.gitignore`）
- 第 11 節第 6、7 條（repo 分工、AI 紀錄欄位）

## 還沒做的

- 共用的 `project.godot`（版本、renderer、解析度）尚未建立
- 第 9 節的客戶聯絡方式尚未寫入
- 客戶訪談的 Q&A 是否三組共享，尚未決定
