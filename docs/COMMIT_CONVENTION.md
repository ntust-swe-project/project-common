# Commit Message 規則

三組各有一個 repo（`group-waterfall`、`group-agile`、`group-AI`），共用內容放在 `project-common`。這份規則存放於 `project-common`，三個 repo 共用。

commit 歷史是報告的證據之一（誰在什麼時候做了什麼、AI 參與了多少），三邊格式一致，才有辦法把三種方法的 log 放在一起比較。

格式採 [Conventional Commits](https://www.conventionalcommits.org/)。

## 格式

```
<type>(<scope>): <subject>

* <body bullet>
* <body bullet>

<footer>
```

- **第一行**：`type(scope): subject`，不超過 72 字元
- **空一行**
- **body**：用 `*` 開頭的條列，一條講一件事
- **footer**：選用，見下方

## type

| type | 用在 |
| --- | --- |
| `feat` | 新增功能（遊戲機制、系統、工具） |
| `fix` | 修 bug |
| `docs` | 文件（需求、UML、會議紀錄、報告） |
| `refactor` | 重構，行為不變 |
| `test` | 測試 |
| `chore` | 雜事（依賴、設定、檔案搬移） |
| `build` | 建置流程、Godot 專案設定、匯出設定 |

只有文件變動就用 `docs`，不要用 `feat`。起始文件、需求規格、UML 都算 `docs`。

## scope

一個 repo 就是一組，所以 scope 不用標組別，標的是「動到專案的哪一塊」。

**三個 repo 都要一致**

| scope | 範圍 |
| --- | --- |
| `vision` | 起始文件（`VISION.md`，在 `project-common`） |
| `req` | 需求分析產出（需求規格、user story、backlog） |
| `uml` | UML 圖 |
| `meeting` | 會議紀錄、客戶訪談紀錄 |
| `ai-log` | AI 使用紀錄 |
| `repo` | repo 結構、README、`.gitignore`、CI |

**各組自訂**

程式碼的 scope（`sim`、`ui`、`colonist`、`crisis` 之類）由各組自己定，但要記在自己 repo 的這份文件裡。三組在這一層命名不同是正常的——那是方法差異的一部分，不用統一。

## subject

- 英文、祈使句、小寫開頭：`add`、`update`、`remove`、`fix`
- 句尾不加句號
- 寫「做了什麼」，不寫「改了哪個檔案」

```
✅ docs(vision): add win and lose conditions
❌ docs(vision): VISION.md 改了一下
❌ docs(vision): updated VISION.md.
```

## body

- 每條 bullet 以動詞開頭，一條一件事
- 可用中文（這是給組員和助教看的），但同一個 commit 內不要中英混寫
- 「為什麼這樣改」比「改了什麼」重要，尤其是推翻先前決定時

## footer

**修改起始文件**

`VISION.md` 定案後若要修改，依文件第 11 節需三組同意。這類 commit 加 `!` 並在 footer 說明同意紀錄：

```
docs(vision)!: change win condition from endless to 30-day survival

* replace endless mode with a fixed 30-day run
* add score summary at the end of a run

BREAKING CHANGE: 影響三組已完成的需求分析。
2026-11-07 討論三組同意，紀錄見 docs/meeting/2026-11-07.md
```

`VISION.md` 只有一份，放在 `project-common`，這類 commit 推到那裡，不要在各組 repo 內另存副本修改。各組 repo 裡出現分岔的 VISION 會讓「三組從同一份輸入出發」這個前提失效。

**AI 參與**

課程要求記錄 AI 使用。若這個 commit 的內容主要由 AI 產生或大幅協助，加上：

```
Co-Authored-By: Claude Opus 5 <noreply@anthropic.com>
```

commit 層面的紀錄不取代 `docs/ai-log/`，只是讓歷史對得起來。

## 範例

```
docs(vision): add midterm project vision document v1.0

* add vision, core experience, and 30-day pacing goal
* add win and lose conditions
* add crisis source categories (external, internal, human)
* add scope boundaries and customer role protocol
* add tech constraints and shared repo policy
```

```
feat(agile): add colonist task assignment

* add priority queue for colonist job selection
* add idle fallback behavior when no task matches
```

```
docs(waterfall): add use case diagram for crisis response

* add actors, use cases, and relations for wave handling
* 依 11/07 客戶訪談紀錄調整，原本漏掉通訊中斷的情境
```

## 可選：commit 範本

每個人在 repo 內跑一次，`git commit` 就會帶出格式提示：

```bash
git config commit.template .gitmessage
```
