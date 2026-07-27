# LEARNINGS — Carrie AI Intelligence

> 每期出刊後 append 一段。下期開工前**必讀全文**。

## Issue 001（2026-07-21 出刊，覆蓋 7 月 14–20 日）

### Fact-check 揪出嘅錯（下期直接避免）

1. **Roundup 炒冷飯係最大陷阱**：三則「當週新聞」其實係舊聞——Karpathy 加盟 Anthropic（5 月 19 日）、Meta AI 助手全球推送（4 月 24 日）、Threads 廣告全球開放（1 月）。**規則：每則新聞都要搜返原始公布日期，唔可以信 roundup 嘅日期。**
2. **「成為預設」「全面推出」呢類字眼最易出事**：GPT-5.6 係「正式開放」但預設仍係 GPT-5.5 Instant。產品狀態（GA／default／beta／announced／rolling out）要逐隻字核實。
3. **市場可用性要逐個 check**：ChatGPT Ads 只開放美日韓，香港落唔到——差啲叫香港讀者做一件做唔到嘅事。**規則：每個 🟢 行動都要核實香港做唔做到。**
4. **Aggregator 來源要升級**：初稿用咗 Tech Startups／LLM Stats／b2the7 呢類二三手來源，全部可以搵到一手（CNBC／OpenAI 官方／Search Engine Land）。搵料時直接加 `site:techcrunch.com OR site:cnbc.com` 呢類 filter 慳返一輪。
5. **數字寫實數好過寫概數**：「三分之一」→「29.45%（SE Ranking，50,032 個關鍵字）」，有研究名同樣本量先似 intelligence。

### 專家 panel 嘅寫作教訓（已寫入 WORKFLOW.md 規則）

- Ghostwrite 嘅親歷聲稱（「I've seen it decide shortlists」）係 IP 信譽炸彈——「I read it as…」安全，「I've seen…」禁用
- 複合預測要拆單（兩個綁埋，錯一半＝全錯）
- 絕對化句子（「cheapest they will ever be」）係最易被斷章取義嘅句子
- 同一期唔好自相矛盾（A 則「兩強競賽」vs B 則「第三勢力崛起」）

### 流程學習

- **環境限制**：proxy 封鎖大部分 WebFetch/curl（chatgpt.com、techstartups、b2the7、甚至 GitHub Pages 站都 403）——一律用 WebSearch snippet 攞料
- **三 agent 並行審核好有效率**（2 個 fact-check + 1 個 panel，~3 分鐘完成），成本遠低過出街後俾人捉錯
- **GitHub integration 冇權開新 repo**（403）——要開 repo 需用戶親手開，然後 add_repo + clone + push
- **Playwright 驗證必做**：render、9 條連結、JS error、中英 toggle，一個 script 搞掂
- 相片處理：用 PIL 以面部為中心裁 800×800 正方形，圓形 crop 先唔會切頭

### 未完成／下期跟進

- [ ] 用戶開通 LinkedIn Newsletter 後，換 `index.html` 兩個 Subscribe 連結（search `Subscribe:` 註釋）
- [ ] Archive 結構：Issue 002 起考慮 `/issues/001.html` 存檔制，首頁永遠最新一期
- [ ] 預測記錄頁（公開追蹤估中／估錯）——panel 認為係建立 authority 嘅最強手段
- [ ] LinkedIn headline 建議同 tagline 統一（已向用戶提出，未確認）

## Issue 001 出街前最終審核（2026-07-21，Editor + 行業專家三席 + 風險審計）

### 新增規則（Issue 002 起生效）

1. **日期窗口誠實**：hero 唔好寫「14–20 July」呢類窗口（一定有新聞跌出窗外俾人捉）——改用出刊日期「Issue 00X · 21 July」
2. **雙語完整性 checklist**：所有 label（包括 Carrie's Take→Carrie 觀點）、所有日期都要有 .zh span；簡體字殘留（着→著）要 grep 一次
3. **標題都要 hedge**：內文有「據報」唔夠，標題先係被 screenshot 嘅嘢——「reportedly／據報」要出現喺標題
4. **產品歸屬要準**：Reels 係 Instagram 唔係 TikTok——平台產品名前面加返公司名
5. **閱讀時間唔好報細數**；訊號圖例（🟢🟡🔴）要有解釋
6. **僱主風險語氣**：行業經濟評論用觀察式（「行業正面對…」）唔用指令式（「agency 應該…」）；footer 常設「個人出版物，不代表僱主」+ AI 協作聲明

### 行業專家評分同 Issue 002 方向

- Agency 讀者 7/10、in-house 讀者 4/10。**最高影響改善：大中華視角要結構化**——每期至少 2–3 則 GC/HK 原生新聞（WeChat／RED／Douyin／travel retail AI），每則全球新聞加「香港角度」一句。呢個係 Carrie IP 嘅 moat，冇咗佢就只係另一份美國科技摘要
- 每則新聞加「Say this to your client」一句（客戶 email 直接用得），係 agency 讀者轉發嘅誘因
- 🟢 每期上限三個（Issue 001 有五個——訊號通脹）；發布 Act/Watch/Wait 準則
- 預測 scorecard 由 Issue 002 開始（上期預測回顧：中／唔中／點解）——冇 scorecard 唔好叫人「Screenshot this」
- In-house 讀者：每個 🟢 加「細團隊版本」動作（無 agency、低預算做法）

### 風險清單（需 Carrie 本人行動，唔係網站改到）

- [ ] **出街前同上司／comms 打招呼**（email，留低回覆）——唯一 career 級風險
- [ ] 換走網站上嘅私人 Gmail（開專用 alias），私人帳戶全部開 2FA
- [ ] LinkedIn About 加「Views are my own」
- [ ] 定期 search 自己名+職銜，望下有冇假冒 profile

## Voice 規則（2026-07-21 語氣審核後定立，永久生效）

Carrie 明確指示：呢個網站係「市場 News + 我嘅觀察」，冇超然或必定嘅 comment。

1. **過去用事實寫，未來用第一身寫**：已發生嘅嘢可以直述（「TikTok 開放咗 Ads Manager」）；未發生嘅一律「I expect／my read is／my bet is／我預期／我的觀察是」，日期保留（accountability），但唔可以斷言（prophecy）
2. **以同行身份建議，唔好做老師**：命令句（「Run a test」「本週請重跑」）改「here's what I'd do」（「我本週會重跑自己嘅 prompts，也建議你照做」）；淨係 Actions 清單同 🟢🟡🔴 label 可以用祈使句（讀者已 opt-in 接受指示）
3. **招牌對比句式保留**：「Most people read X, I read Y」「a bet, not a plan」係品牌——自信來自觀察嘅銳利，唔係動詞嘅必然
4. Prediction 收尾用 accountability hook（「Check back on me in January — I'll own it either way」），唔用「Screenshot this」先知式
5. **Footer 一句搞掂**：全部聲明壓縮做一行 muted 細字（© · 個人觀點 · AI 輔助經審閱 · 附原文出處），詳細版放 About——結尾唔可以累贅

## 預測準則（2026-07-21 Carrie 定立，永久生效）

**冇實在支持嘅推測，寧願唔出。** 每個 prediction／expectation 出街前過三關：

1. **有冇可驗證嘅依據？**（觀察到嘅 pattern、數據、已發生嘅 sequence）——類比唔算證據（multi-cloud 類比嗰個預測因此刪走）
2. **依據要寫埋出嚟**（「The basis: …／依據：…」），俾讀者自己判斷推論強唔強
3. **依賴第三方未公布決定嘅預測唔好出**（例：「ChatGPT Ads 登陸香港後兩季內…」——OpenAI 未公布香港時間表，刪走）

Issue 001 應用結果：三個預測刪剩一個（lookalike audiences——有 Meta 劇本 sequence + custom audiences 技術前設做依據）。**質素標準：一個有依據嘅預測，好過三個冇依據嘅。**

## Issue 001 終審決定（2026-07-21）

- **📈 分類招牌暫時用中性描述**（"and what I'd do about it"）——「香港及大中華視角」呢個招牌要等 Issue 002 真係有 2–3 則 GC 原生新聞先掛返上去，招牌唔可以走喺內容前面
- Post 承諾寫 "every week" 唔寫 "every Monday"（出 post 日係週二／三，唔好自己打倒自己）
- LinkedIn post 嘅 first comment 加常設一句「Personal project — views mine, not any employer's or client's」
- 出街日應對小抄同 24 小時 playbook 已存喺 linkedin-post.md 尾段，每期出 post 前重溫

## 編輯方針改版（2026-07-21 Carrie 決定，永久生效）

**網站唔用個人掛名觀點。** Carrie 原話：「我想個網站資訊性要夠強，而我嘅觀點又唔一定啱，所以我會採取資料性、重要性、行業洞察，唔用 Carrie's take，費事講錯嘢俾人周。」

新卡片結構（Issue 001 已重造，之後照跟）：
1. **Key Highlights／重點摘要**：2–3 粒 bullet，事實＋重要性融埋寫（取代 Summary + Why it matters 兩段）
2. **Industry Insight／行業洞察**：1–2 句中性行文——冇「我／I」、冇個人掛名，保留 hedge
3. **Pattern Watch／趨勢觀察**（取代 My Prediction）：有實據 pattern 先寫，中性行文（「值得留意」），冇個人承諾式收尾
4. LinkedIn post 係個人發言可用第一身，但預測同樣用 pattern-watch 式

其他當日決定：
- **WAICO 補入 Issue 001 做第 10 則**（29 國 7 月 16 日上海簽署、政府間組織、已 fact-check：gov.cn + Al Jazeera + Sixth Tone 三源核實）——Issue 001 由此有咗第一則 GC 原生新聞
- 漏網新聞覆盤：Thinking Machines Inkling（975B open-weight）同 Kimi K3 撞主題冇入；小紅書聚光「爆文拆解／簡單投」+ 蒲公英新規來源未夠實（搜狐/網易級數），列入 Issue 002 候選待驗證

## 清晰度規則（2026-07-21 Carrie feedback 後定立，永久生效）

Carrie 指出洞察段「表達唔清晰、前文後理難以理解」（例：Atlas 嗰段「賭博而不是計劃／平台層／side projects」）。問題根源係**壓縮式寫法**。新規則：

1. **每段洞察要自足**——一個冇睇過前文嘅讀者都要即刻明；指涉要明確（「教訓」係咩教訓？「平台層」即係邊啲產品？）
2. **少用壓縮比喻**（「賭博而不是計劃」呢類）——直接講清楚因果：「呢類產品隨時會被叫停，所以唔好依賴」
3. **術語節制**：marketer 圈通用術語（SEO、prompt、lookalike audiences）可以用；含糊嘅抽象詞（平台層、visibility strategy、stack、決策價值）要換做具體講法或者即場解釋
4. **寫完自測一次**：「唔知前文嘅讀者，單睇呢段明唔明？」唔明就重寫

## 最終來源覆核結果（2026-07-21 晚，出街前最後把關）

10 則逐 claim 覆核（26 次搜尋、全部附證據 URL），8 則完全 VERIFIED，2 個修正：
1. **ChatGPT Ads 市場清單寫少咗**：實際已開放 7 個市場（美加英澳紐日韓），我哋只寫咗 3 個——教訓：**「可用市場」呢類清單要搵最新完整名單，唔好照抄舊報導**
2. **Atlas「7 月 14 日確認時間表」查無實據**（死線 7 月 9 日已公布）——教訓：日期 metadata 都要有來源，冇來源就刪
另外注意：Kimi K3「明顯平過同級」係成立但偏進取（vs 旗艦平三分之二，但同中階模型同價）——下期呢類比較寫明對比對象。

## 受眾定位（2026-07-22 Carrie 確認，永久生效）

**中文版讀者 = 香港（主）+ 台灣 + 海外華人。大陸用戶唔係目標讀者**——LinkedIn 喺大陸用唔到，佢哋根本接觸唔到呢份簡報。

執行含義：
1. **語言維持「香港書面中文」**：繁體＋行內英文詞（prompt／workflow／agency）——呢個係 Carrie 把聲嘅一部分，唔使為接觸唔到嘅讀者中性化；唔出簡體版
2. 「營銷」照用（香港用法），台灣讀者睇得明，唔為單一詞分裂版本
3. **重要區分：大陸讀者 ≠ 大陸內容**——讀者係香港/台灣 marketer，但佢哋好多做緊大陸市場生意，所以 WeChat／小紅書／巨量引擎／中國 AI 監管呢啲 GC 內容線照跟，一啲都唔減——嗰個係內容 moat，唔係受眾問題
4. 將來如果分發渠道擴展（例如 WeChat 公眾號版），先重新檢視簡體需求

## 底部 section 改「問題」不「命令」（2026-07-22 Carrie feedback）

Carrie 指出原本「Don't curate news. Curate decisions.」下面三個 action（Build / Check / Write your…）**太強（命令句）＋唔關讀者事**（假設讀者係有客戶嘅 agency：top 3 clients／in a pitch／your team——但一半受眾係 in-house／細團隊）。

改法（永久生效）：
- 標題改「Three questions this week raises／本週值得思考的三個問題」
- 副題明講「Not a to-do list… whether you sit in an agency or on the brand side／無論你在 agency 還是品牌方」——修正受眾假設
- 三項由命令句改**問題句**（「Do you have…？」「How do…？」「Could your team…？」）＋一句中性 context——informational，唔說教，agency/品牌方都成立
- Label 由動詞（PREPARE/AUDIT/GOVERN）改名詞主題（AUDIENCE DATA／BRAND VISIBILITY／AI GOVERNANCE）；nav 由「Actions」改「Worth Asking／值得思考」

原則：呢個 section 係全站最後一個命令式殘留——同「網站唔用個人掛名觀點、informational 不說教」嘅定位對齊。以後底部永遠用問題形式。

## 中文避免翻譯腔（2026-07-22 Carrie feedback 後定立，永久生效）

Carrie 指出部分中文「唔夠 native」（例：「面對這些新廣告平台越來越倚重的 first-party 數據，你手上準備好了嗎？」）。根源係**照搬英文句構**。中文 editor 掃全站捉到 7 句，集中喺後加/重寫嘅段落。

寫中文時避開嘅翻譯腔 marker：
1. **長前置修飾語**（英文 relative clause 搬過嚟：「這些…越來越倚重的…數據」）→ 拆短，用 topic-comment，先講重點
2. **「面對…」「隨著…」「對於…而言」骨架** → 母語作者多數會刪
3. **被動 calque**（「正在被決定」）→ 改主動（「由這幾間公司拍板定案」）
4. **名詞化堆疊**（「…的準備」「…的提升」）→ 改動詞（「先把…準備好」）
5. **動賓搭配唔啱**（準備好+冇賓語、留下決策）→ 補返賓語或換講法
6. **英文詞直譯**（「一頁答案」= one-page answer）→ 「一份一頁紙的答覆」
**自測**：每句中文問「一個母語讀者會唔會咁講？」——起草後、以及任何後加/重寫段落，都要再過一次（翻譯腔最常喺趕住補寫嘅段落出現）。

## LinkedIn post 語氣：平實分享，唔扮野（2026-07-22 Carrie 決定，永久生效）

Carrie 明確：post 唔想「扮野」，只想「sharing news with all of you」。原本嘅 post 太長（~290 字）＋太 thought-leader（manifesto hook、"I read the news so you don't have to"、"my bet／my play"、"one brief not fifty headlines" flex）。

新語氣（Issue 001 已改，之後照跟）：
1. **平實開場**（「呢星期有幾則 AI 新聞我覺得值得留意，分享畀大家」），唔用 manifesto/hot-take
2. 3 則 takeaway，每則一句事實＋一句**輕解讀**（"worth knowing"／"a good nudge"／"one to watch"）——唔用「my bet／我預期」權威口吻
3. **連結直接放正文**（Carrie 決定唔玩「first comment 谷 reach」嗰套；出街嗰次佢用咗 link-in-comment 版，兩者都得，going forward 用正文）
4. 平實收尾（"just sharing what I've been reading, hope it's useful"）＋短免責（"Personal project — views my own"）
5. 長度 ~170 字；hashtags 5–6 個
6. **唔搞 engagement 谷數**：唔夾人留言、唔 DM 谷 comment（Carrie 明確唔要）——真心分享，出咗就算

紅線：唔扮權威、唔 sales flex、唔高高在上。係「同行分享」，唔係「專家指點」。

## Issue 002（2026-07-28 出刊，覆蓋 7 月 20–26 日）

### Fact-check 揪出嘅錯（下期直接避免）

1. **舊聞陷阱再犯一次，即使 Issue 001 已經寫低教訓**：Meta「AI 廣告標籤收緊」一則，實際原始政策係 6 月 1 日、報道係 7 月 9 日，唔係當週新聞——被二手 wire 稿（Marketing Dive/Sociable）包裝到似係本週新聞。Fact-check agent 揪出後即刻換咗做騰訊 Miora（7 月 22 日全量上線，一手 Tencent News 來源）。**規則：凡靠二手／aggregator 報道搵到嘅料，起草前就要先追溯返最原始嗰篇公司公告嘅日期，唔好等 fact-check 先發現。**
2. **公司官網會有多篇主題相近但日期唔同嘅文章**：OpenAI 關於「點樣落 ChatGPT 廣告」呢個主題，5 月同 7 月各出過一篇官方 blog post，起草時錯引咗 5 月嗰篇當做 7 月 22 日 GA 嘅來源，順帶將 5 月先出嘅 CPC bidding 功能寫成「呢星期新增」。**規則：引用公司官網做來源時，一定要核實嗰條 URL 本身嘅發布日期，唔好淨係睇主題啱唔啱。**
3. **中文大數字換算出錯**：小紅書 RED Skill 開發者人數，多個一手來源標題都寫「7300個Skill、16萬開發者」，起草時「16萬」被誤讀/誤打成「1,600」——即差咗 100 倍。**規則：中文標題入面嘅萬／万呢類單位，抄錄後要用計數機心算一次核實，唔好掃描式閱讀。**
4. **定價比較物件要準**：Claude Opus 5「平前代一半價錢」呢個講法，原意其實係「Opus 5 平 Fable 5 一半」，Opus 5 本身同 Opus 4.8 定價不變——起草時將比較物件搞錯咗。**規則：定價／規格類比較句，要寫明「邊個 vs 邊個」，唔好用「its predecessor」呢類代名詞簡化，容易張冠李戴。**
5. **Hedge 校準都要留意「太保守」嗰面**：Moonshot 制裁一則，初稿寫「據報財政部考慮緊制裁」，但財政部長 Bessent 本人已經公開表態「制裁都在考慮之列」——呢個唔係要加 hedge，而係要拆返「reportedly」，直接歸屬俾佢本人嘅公開發言。**規則：hedge 語氣兩個方向都要核實——唔止「敢唔敢講死」，仲有「講得夠唔夠準」。**

### 專家 panel 揪出嘅殘留問題

- Footer 常設一句「interpretations are mine」，同 2026-07-21 定立嘅「網站唔用個人掛名觀點」規則有牴觸——呢句由 Issue 001 一直留到而家先俾 panel 捉到。**已喺 Issue 002 footer 刪走，改做「Stories link to original sources.」**——下期記得順手檢查 Issue 001 需唔需要同步（歷史檔案，暫時未動）。
- 「值得思考」第二條問題用咗「client work」呢個 agency 專屬字眼，panel 指出品牌方／in-house 讀者唔會咁講自己嘅產出——改咗做中性嘅「a piece of work」。

### 流程學習

- **三 agent 並行審核（2 fact-check + 1 panel）今期做得更徹底**：兩個 fact-check agent 各自跑咗 30+ 次搜尋（合共 233 秒同 364 秒），撈出 1 個要命嘅日期錯誤（Meta 舊聞）、1 個 100 倍嘅數字錯誤、1 個引錯 URL、2 個定價／歸屬校準——證明呢個步驟嘅投資報酬遠高過出街後被人捉錯。
- Fact-check agent 之間有分工重疊都無妨（例如兩邊都提到 hedge 校準），交叉核對反而加強咗信心。
- Playwright 驗證流程行咗兩次（改完 headline 入面殘留嘅舊數字先發現漏咗一處），提醒：**改完 Key Highlights 入面嘅數字，一定要順手 grep 埋標題／badge 有冇同一個數字嘅重複版本**，唔好淨係改一處就當搞掂。

### 未完成／下期跟進

- [ ] Issue 001 嘅 footer「interpretations are mine」歷史殘留，未同步修正（歷史檔案，需 Carrie 決定要唔要動）
- [ ] 用戶開通 LinkedIn Newsletter 後，換 `index.html` 兩個 Subscribe 連結（search `Subscribe:` 註釋）——沿用上期未完成事項
- [ ] Pattern Watch 呢期做咗兩個（HF breach × AI Safety Index 對照；ChatGPT Ads self-serve × Meta playbook 追蹤）——下期繼續追蹤 lookalike audiences 有冇正式上線

## Issue 002 出街後 Carrie feedback（2026-07-27，永久生效）

**問題**：Carrie 指出 Issue 002 嘅「OpenAI 將 ChatGPT 廣告正式向公眾開放——香港仍未在名單上」呢則，同 Issue 001 已經開過嘅「ChatGPT Ads 悄悄開放 Custom Audiences」太似——兩則都係「ChatGPT Ads 呢條產品線又有新進展」，連續兩期都開晒做正選 headline，讀者會覺得重複。

**根源**：起草 Step 1 研究嗰陣，冇檢查返上一期／上上期已經開過嘅新聞標題／連結，淨係核對咗「呢則新聞本身係咪當週新聞」，冇核對「呢條產品線上期開唔開過」。

**新規則（已寫入 WORKFLOW.md Step 2 寫作規則第 7 條，永久生效）**：
1. 起草前，將上一期同上上期嘅全部標題／連結列出嚟做一次對照
2. 同一條產品／功能線（例如「ChatGPT Ads」「Xiaohongshu RED Skill」）如果上期已經開過正選新聞，呢期得返漸進式細更新（加功能、擴市場、數字微升），**唔開新 headline**，改用 Pattern Watch 或者喺其他相關新聞嘅 Key Highlights 一句帶過
3. 只有重大進展（beta→GA、市場覆蓋大幅跳升、方向逆轉、監管介入）先值得重開新 headline，並且標題／首個 bullet 要講明係跟進（例如「继…之後」），唔好當做全新獨立新聞包裝
4. Pattern Watch 本身就係為咗解決呢個問題而設嘅機制（見 Issue 001「編輯方針改版」）——呢次教訓係：**Pattern Watch 唔夠，仲要喺選題階段就主動避免同一條線連續兩期攞正選位**

## Issue 002 追溯修訂（2026-07-27，Carrie 要求換走 ChatGPT Ads 則）

上一節寫低 rule #7（向前生效）之後，Carrie 進一步決定：唔止下期避免，今期都要**換走**「OpenAI 開放 ChatGPT 廣告」嗰則，並且「兩則都加」（Gartner + Alphabet），Issue 002 由 10 則變 11 則（MARKETING IMPACT 4 則）。呢次係一個「已出街後追溯改稿」嘅完整案例，下次照跟：

**選題／研究：**
1. **替補新聞一定要喺同一期覆蓋窗口內**（20–26/7）——唔可以貪新搵 27/7 或之後嘅，否則變成成期唯一超出自己覆蓋週嘅一則，反而穿崩。天花板 = 覆蓋週最後一日。
2. **roundup 炒冷飯陷阱又中一次**：Meta AI 廣告助手（實 4 月）、TikTok Agentic Hub（6 月 30）、SparkToro 零點擊研究（6 月 8）、阿里媽媽 AI萬相（3 月）全部被 7 月 roundup／每日彙整包裝成當週。每日新聞彙整（bestmediainfo／marketingtech 呢類）啱用嚟搵線索，但**每條都要追返一手嘅原始日期**先揀到真正 in-window 嘅 Gartner（7 月 20 官方 press release）同 Alphabet Q2（7 月 22 業績）。
3. Carrie 質疑「呢啲會唔會耐得滯」——好提醒：追溯改稿要主動同佢講清楚替補點解 in-window（同期其他新聞一樣新，例：Alphabet 同已收貨嘅騰訊 Miora 都係 7 月 22），順便交代篩走咗邊幾條真·舊聞，佢先安心。

**Fact-check（又一次值回票價）：**
4. 揪出「只有 18% 企業見到 AI 收入影響」唔係 Gartner 嗰篇，係 HCLTech（7 月 21）——roundup 將兩份同週報告溝埋，已剔走。另：Gartner「117%」係 GenAI 模型總線，唔好誤標做 foundation model（嗰個係 104.2%）。
5. AI Max/PMax「+15% 轉化」係業績電話會嘅正確數字；product-page 另有個 +7%（窄口徑，唔同嘢）——揀啱嗰個，唔好被 7% 誤導。

**整合／連帶清理（追溯改稿最易漏）：**
6. 連續兩期 Google 搜尋廣告線（Issue 001 開過「AI Mode ads」）嘅處理：Alphabet 嗰則用 **Pattern Watch 明確承接 Issue 001**，將「重複」轉做「跟進 payoff」（rule #7 容許嘅做法），唔係當全新獨立新聞。
7. **改／換一則新聞後，一定要全站 grep 佢嘅連帶引用**：hero「本週訊號」、封面 desc + 故事數（10→11）、閱讀時間、LinkedIn takeaway + crib + hashtag、「值得思考」section。今次順手捉到兩個 dangling ref：action 02 仲掛住已被換走嘅「Meta 廣告標籤」（由 0002 patch 一路留到而家先發現）、action 03 掛住 ChatGPT Ads——一併重錨。**新內部規則：每次換／改新聞後，grep 全站有冇留低已移除故事嘅引用。**

## LinkedIn post + 封面每期硬性交付（2026-07-27 Carrie 常設要求，永久生效）

Carrie 明確：**每次出 issue，都要連同英文 LinkedIn post 內容 + post image 一齊交俾佢出 post。** 已寫入 `SKILL.md` 不可妥協規則同 `WORKFLOW.md` Step 8：完工時一定要用 `SendUserFile` 交 ① 英文 LinkedIn post 全文（可直接 copy）② 當期英文封面 PNG——每期必做，唔使等佢開口。

## 中文 native 度 editor sweep（2026-07-27，Carrie 覺得中文似英譯後）

Carrie 反映網站中文「唔夠 native、似由英文硬譯」。派咗一位資深香港繁體中文編輯 agent 掃全站，整體評 7/10，改咗 23 處。翻譯腔集中喺長句 Industry Insight／Key Highlights，主要四類（下期起草時直接避開）：
1. **代名詞硬譯**「它的／其」（its／it）——中文母語多數會刪
2. **長前置定語／名詞化套疊**（英文 relative clause 成段塞喺名詞前，例如「首宗…的案例」「所需的研究成本」）——拆短、用冒號、topic-comment
3. **英式骨架「對（於）…而言」濫用**（一版用咗 4 次，其中兩則 mkt 新聞開頭一模一樣「對香港及大中華的營銷人而言」）——變化講法，唔好連續同一開頭
4. **廣東話口語**（細型／細團隊／識編程／有經營）同**內地用詞**（全量開放／自研／跳轉）滲入——違反「香港書面中文、唔准廣東話口語」硬標準
**最重要教訓：新加／後補嘅新聞段落最易中翻譯腔（今次 Gartner／Alphabet／hero 三段都有），所以 editor sweep 唔止掃舊內容——邊段最新寫、最趕，邊段就最要過。** 下期可將呢四個 marker（的的不休、它的/其、對…而言、廣東話/內地詞）加入 WORKFLOW Step 6 嘅 grep 清單。
