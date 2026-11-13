# VeilProof（隱證）商務兵棋推演／沙盤推演模擬模組 產品說明與預售內容

| 欄位 | 內容 |
| :--- | :--- |
| 產品線名稱 | VeilProof（隱證）商務兵棋推演／沙盤推演模擬模組（`allview-market-simulation-app`）。**對外正式中／英文名稱 [待確認]** |
| 產品線編號 | [待確認] 10 條產品線中的編號尚未提供；README 未載明 PMO 倉儲代碼（如 `C3-AV-xxx-F`／`C2-AV-xxx`）[待確認] |
| 所屬法人 | 事業體 AllView／全視界（domain：`allview.today`；PMO：`C1-AV-CORP`）。**正式法人名稱（公司登記名稱）[待確認]** |
| 產出日期 | 2026-11-13（Asia/Taipei） |
| 版本 | 草稿 v0.2.1 |
| 任務目標 | [假設] 同時更新 README 與產出預售說詞（使用者僅附上檔案，未另行指定範圍） |
| 核心事實錨點 | 使用者於 2026-11-13 將對外正式名稱定為「密文智庫 / EncryMind」，並決定同時以該名稱取代「亞傑師私有金庫 / AEGIS Vault / AEGIS-Vault」產品顯示名稱，為 v0.2.1 新增事實錨點；本次未另附獨立錨點。下文事實均摘自使用者提供之既有 README，**尚未升級為已確認錨點** |

v0.2.1（2026-11-13，Asia/Taipei）：依使用者 2026-11-13 指示，對外產品顯示名稱由「FHE AI NAS」及「亞傑師私有金庫 / AEGIS Vault / AEGIS-Vault」統一為「密文智庫 / EncryMind」。僅替換散文、標題與表頭中的顯示名稱；repo 名稱 AEGIS-Vault、org、產品代號、檔名主體、URL、CTA 代碼、分支與程式識別字不變。其餘內容不變，仍為草稿。

v0.2（2026-11-10）：依主 PMO 確認統一品牌名稱與官方網域為 斜槓一二三 / Slash123（slash1to3.com）、斜槓104 / Slash104（slash1ofours.com）、水月道場 / Wonderland Center（wonderland.center）；僅移除官方網域選擇的待確認標註，其餘待確認與內容維持草稿

---

## 1. 輸入確認

- **產品線名稱／代號**：VeilProof（隱證）商務兵棋推演／沙盤推演模擬模組；功能倉 `allview-market-simulation-app`
- **所屬法人**：README 寫明本倉為 AllView（`allview.today`）數位傳播與互動技術生態矩陣下的第三類功能性技術儲存庫；GitHub 組織為 `allview-today`；角色信箱均為 `@allview.today`。
- **跨事業體出現之處（須分開標註，不改變歸屬）**：
  - 資安漏洞通報信箱寫為 `github-security@wonderland.center`（wonderland.center 網域）。[待確認] 是否為正確的對外資安窗口，或應改為 AllView 網域。
  - README 的 FHE 函式庫為 OpenFHE／TFHE-rs，**未**提及 AEGIS（`aegis.expert`）的 FHE 核心。[待確認] 是否與 FHE Social 一樣，FHE 核心實際由 AEGIS 協作提供。
- **既有文件**：`allview-market-simulation-app` README（定位、功能矩陣、密碼學邊界、目錄、本地開發、QA 閘門、協作規範、信箱、授權聲明）
- **對應預售倉**：`allview-market-simulation-presale`（README 架構圖中標示為 Presale Showcase Repo）
- **核心事實錨點**：未另提供
- **本次任務目標**：[假設] README 更新 + 預售說詞

---

## 2. 分析與標記

### 可保留內容（結構清楚、可作為草稿基礎）

- 定位：面向**商戰對決、併購談判、供應鏈博弈、反壟斷調查與危機公關**的多方沙盤推演與決策訓練引擎。
- 三項設計原則：策略不可知（底牌以 FHE 密文參與運算）、行動不可否認（動作簽章與因果鏈）、偽匿名互動。
- 八大模組 [A]–[H] 與 MOD-01～MOD-08：模式控制（自我對自我／AI+真人／匿名多方配對）、沙盤（多層視圖、What-if 分支）、談判核心（ZOPA、BATNA、施壓倒數、欺敵）、FHE 策略引擎、證據鏈、AI 對手、覆盤與個案脫敏匯出、角色權限與「訓練／實戰」模式。
- 密碼學邊界：客戶端加密 → 不受信任運算節點密文碰撞 → 僅揭露必要布林狀態（成交／未成交／臨界警報）→ 簽章寫入 Merkle Action Block。
- 兩條紅線：禁止底牌明文上傳（僅 TLS 也不行）；FHE 只跑預先定義的固定電路，LLM 對話走隔離的受控推論，不做全量 FHE NLP。
- 免責聲明：AI 提示、勝率估算與策略建議僅供商務決策訓練與教育參考，不構成法律、投資或併購操作保證。
- Gate 0～6 QA 閘門、協作分支規範、角色信箱。

### 易混淆／缺證據之處

- **徽章**：`CI/CD Passing`、`Security Audit Ready`、`QA Gates Gate 0 to Gate 6`、`PRs Welcome` 為 README 徽章，**不代表**已完成外部稽核或已達成全部閘門。對外一律 [待確認]，本草稿 README 建議版已移除狀態型徽章。
- **「Signal 級端對端加密」「Signal Protocol 級雙向會話棘輪」**：比較級宣稱，未附第三方驗證。改寫為「採雙向會話棘輪（Double Ratchet）設計 [待確認]」，不對外使用「Signal 級」。
- **「極限商戰心理攻防」「密碼學級因果鏈」「杜絕運營方或任何對手偷窺底牌」**：程度語或絕對化表述，改寫為可驗證語句；「杜絕」改為「設計上運算節點不接觸明文底牌」[待確認]。
- **「VeilProof 原有的技術底座」**：README 稱本模組基於 VeilProof 原有能力（易用性 + E2EE + 偽匿名身分鏈 + 證據鏈）擴展。這與 AllView FHE Social 的能力描述高度重疊。[待確認] VeilProof 原產品與 FHE Social 的關係（同一底座？不同產品？），以及「VeilProof」是品牌名還是本模組名。
- **即時制（Real-time）與 FHE 運算延遲**：README 同時支援即時制，又要求所有底牌走 FHE；Gate 5 提到「延遲符合 SLA 門檻」，但未給任何數字。即時性與延遲 [待確認]，不得對外承諾。
- **「監管方加入」「反壟斷調查」「法律教學與仲裁」**：README 提到可用於仲裁與法律教學，但免責聲明又說不構成法律依據。[待確認] 證據鏈在仲裁場景的法律效力，預售文案不寫「可作為法律證據」。
- **AI 對手「具備詐術」**：屬訓練用途的虛擬對手設定；對外措辭建議改為「模擬欺敵與施壓風格」，避免誤解。
- **單元測試覆蓋率 >= 80%**：屬 Gate 2 內部工程門檻，非對外品質承諾。

### 目前缺失的關鍵資訊

- 正式法人登記名稱、產品線編號、PMO 倉儲代碼（README 未給 C2/C3 代碼）
- 獨立的核心事實錨點
- 商業化狀態（規格／開發中／可演示／可交付）、銷售模式（SaaS／授權／專案制／教育方案）、價格、交期、SLA [禁止自行假設]
- 支援的人數上限、回合制／即時制的實際延遲、FHE 參數與效能基準（README 只列 `crypto-bench` 測試目錄，無數據）
- FHE 核心是否由 AEGIS 協作提供
- 授權條款（README 寫「閉源授權或指定開放授權」，未定案）
- 「VeilProof」與 FHE Social 的品牌關係

---

## 3. 產品概述

VeilProof（隱證）商務兵棋推演模組是 AllView（`allview.today`）規劃中的多方商務沙盤推演與決策訓練引擎，涵蓋商戰對決、併購談判、供應鏈博弈、反壟斷調查與危機公關等情境。參與者可以自己推演、與 AI 對手對抗，或在偽匿名狀態下與真人多方配對；沙盤提供戰略大盤、供應鏈拓撲與現金流曲線等視圖，並可從任一節點分出 What-if 分支。

它與一般商業模擬遊戲的差別在於「底牌保密」與「動作可舉證」：底線成本、讓步階梯、預算上限等敏感數字在客戶端加密後，以全同態加密（FHE）密文參與比對，運算節點只回傳必要結果（例如成交／未成交／臨界警報）；每一次出價、施壓與查看動作都附上數位簽章並寫入 Merkle 狀態鏈，供事後覆盤與個案教學。實作完成度、即時性與效能數據均 [待確認]。

---

## 4. 核心特性與功能（可驗證者優先）

以下摘自 README 模組表，實作完成度均為 [待確認]。

1. **推演模式（MOD-01）**：回合制與即時制；1v1、多方聯盟、監管方加入的動態配對；自我對自我、AI+真人、完全匿名多方配對。[待確認] 即時制在 FHE 運算下的實際可用性。
2. **沙盤（MOD-02）**：多層級視圖（戰略大盤、供應鏈拓撲、現金流曲線）；分支樹（Branching／What-if）模擬。
3. **談判核心（MOD-03）**：結構化談判協議，含 ZOPA 探索、施壓倒數計時器、BATNA 替代方案威脅、資訊不對稱欺敵。
4. **FHE 策略引擎（MOD-04）**：多方密文交集、成本區間重疊比對、勝率估算，不接觸明文。限定於預先定義的固定電路（比較器、多項式評分、加權矩陣）。
5. **證據鏈（MOD-05）**：雙向會話棘輪與不可竄改操作簽章（Signed Action Records）、Merkle 狀態鏈、授權密鑰揭露。README 原文稱「Signal Protocol 級」，對外比較語 [待確認]。
6. **AI 對手（MOD-06）**：本地或受控模型推理，可設定激進／保守／欺騙風格；訓練模式下提供即時策略熱度圖提示。LLM 不跑 FHE，走隔離受控推論。
7. **覆盤與個案工作室（MOD-07）**：互動時間軸覆盤、關鍵決策節點標記、敏感資料脫敏後匯出為教學個案；README 提及「社群論壇整合」[待確認] 整合對象。
8. **角色與模式守衛（MOD-08）**：教練／觀察員／選手角色權限；「訓練模式」允許 AI 雷達提示，「實戰模式」屏蔽提示並強制防作弊檢查。

---

## 5. 目標銷售對象

README 列出情境類型，但未定義客戶規模、產業或採購角色；以下對象描述中帶 [假設] 者為推論，需確認。

**對象 A：需要演練高敏感談判的企業團隊**

- 情境：併購談判、供應鏈議價、危機公關演練。
- 需求：在演練中放入真實或接近真實的底線數字，但不希望對手方、教練甚至平台運營方看到明文。
- [假設] 採購窗口可能是策略部門、企業發展（Corp Dev）、採購談判團隊或公關危機小組。

**對象 B：商學／法律教學與企業培訓機構**

- 情境：以角色扮演方式教授談判、競爭策略或反壟斷情境，並需要可回放、可脫敏的教學個案。
- 需求：教練／觀察員／選手分級權限、覆盤時間軸、個案脫敏匯出。
- [假設] 商學院 EMBA、談判課程講師、企業內訓單位。

**對象 C：個人自我訓練者**

- README 支援「自我對自我」與「AI+真人」模式。[待確認] 是否開放個人方案。

**非對象（依 README 可合理區隔，供審核）**

- 需要正式法律意見、投資建議或併購執行依據者：README 免責聲明明確排除。
- 需要醫療決策、臨終照護選擇演練者：屬 Wonderland Center 選擇預演，非本產品。
- 只需要匿名社群或加密通訊者：屬 AllView FHE Social，非本產品。

---

## 6. 差異化定位

**同法人（AllView）相鄰產品**

- **vs. AllView FHE 匿名與不可否認社群（FHE Social）**：兩者都用 FHE、偽匿名與不可否認簽章，最容易混淆。FHE Social 是終端使用者的社群／知識交流與通訊空間；VeilProof 隱證是有規則、有回合、有勝負與覆盤的**商務推演引擎**，FHE 只用在底牌比對的固定電路上。[待確認] 兩者是否共用底層元件。
- **vs. 寰境再製（OrbiLocale）**：OrbiLocale 交付多語內容再製包，與推演無關；兩者僅同屬 AllView 事業體。

**跨法人易混淆產品**

- **vs. 選擇預演（ChoiceRehearsal，Wonderland Center）**：選擇預演是醫療／預立醫療決策的教育與決策輔助，非醫療行為；VeilProof 隱證是商務談判與競爭推演。兩者都有「預演／沙盤」意象，對外須明確分開，不可互相引用。
- **vs. HEShell、密文智庫（EncryMind）（AEGIS）**：兩者是 FHE／AI 的安全殼層與地端運算節點，屬基礎設施；VeilProof 隱證是應用層的推演產品。若 FHE 核心由 AEGIS 提供，屬跨事業體協作，[待確認]，不改變本產品歸屬 AllView。

**相對於一般商業模擬或談判訓練工具**：差異點是「底牌以密文參與比對、只揭露必要結果」與「每個動作可簽章回放」，而不是畫面或劇本數量。效能、可支援人數與即時性未提供，不作比較。

---

## 7. 預售說詞（草稿，可直接改用）

> 以下文案只陳述 README 中已寫明的設計範圍，不包含價格、交期、效能保證、第三方稽核或法律效力表述。

### 短文案（企業談判演練情境）

談判演練最難的是放進真實數字：底線、預算上限、讓步順序一旦外流，演練本身就變成風險。VeilProof 隱證的設計是讓這些數字在你的裝置上先加密，再以密文參與比對；系統只回報「是否進入可成交區間」這類必要結果，不把底牌攤開給對手或平台。每一次出價與施壓都會留下簽章紀錄，演練結束後可以逐步回放、找出關鍵轉折。

### 短文案（教學與培訓情境）

用沙盤教併購、供應鏈議價或危機公關時，講師需要的是可控的角色、可回放的過程與可再利用的個案。VeilProof 隱證提供教練／觀察員／選手三種角色、訓練與實戰兩種模式，並能把一場推演的時間軸脫敏後匯出成教學個案。AI 對手可以設定激進、保守或欺敵風格，讓學員面對不同類型的談判對象。

### 賣點句

- 底牌不攤牌：敏感數字以 FHE 密文參與比對，只揭露成交／未成交等必要結果。
- 動作可回放：出價、施壓、查看紀錄皆簽章並串成狀態鏈，供覆盤與教學。
- 情境貼近實務：ZOPA、BATNA、施壓倒數、資訊不對稱與 What-if 分支都在同一張沙盤上。
- 訓練與實戰分開：訓練可開 AI 提示，實戰屏蔽提示並做防作弊檢查。
- 可轉成個案：推演紀錄脫敏後匯出為教學素材。

### FAQ 草稿

**Q：平台看得到我們輸入的底線數字嗎？**  
A：設計上不行。底牌在客戶端加密後才送出，運算節點只在密文上比對，且 README 明訂禁止底牌以明文或僅 TLS 加密的方式送達伺服器。[待確認] 是否有第三方稽核報告可對外提供。

**Q：AI 對手的對話也是加密運算嗎？**  
A：不是。FHE 只用於預先定義的比較、評分與加權計算；AI 對手的自然語言對話走隔離的受控推論。這是刻意的設計邊界，對外應如實說明。

**Q：推演紀錄可以拿來當法律證據嗎？**  
A：不建議這樣主張。紀錄有簽章與狀態鏈，可用於覆盤與教學；但本產品明確聲明不構成法律、投資或併購操作依據。在仲裁場景的效力 [待確認]。

**Q：支援即時對戰嗎？可以幾個人同時推演？**  
A：README 記載支援回合制與即時制、1v1 與多方聯盟，但未提供延遲或人數上限數據。[待確認]，確認前請勿對外承諾。

**Q：跟 AllView 匿名社群（FHE Social）有什麼不同？**  
A：社群是交流與知識空間；VeilProof 隱證是有規則、有回合與覆盤的商務推演工具。

**Q：多少錢、何時可以用？**  
A：本次未提供價格、方案與上線時程，暫不對外陳述。

---

## 8. 建議的 README.md 完整更新版

下列為建議用來更新 `allview-market-simulation-app`（及預售倉 `allview-market-simulation-presale` 可引用之產品說明）的 README 草稿。已移除狀態型徽章與比較級措辭，未確認項目加上標記。

```markdown
# VeilProof（隱證）商務兵棋推演／沙盤推演模擬模組

> **功能倉儲**：`allview-market-simulation-app`（PMO 代碼 [待確認]）  
> **預售倉儲**：`allview-market-simulation-presale`（PMO 代碼 [待確認]）  
> **所屬法人／事業體**：AllView／全視界（`allview.today`；PMO `C1-AV-CORP`）｜正式公司登記名稱 [待確認]  
> **文件狀態**：草稿，待人工審核

## 這是什麼

VeilProof（隱證）商務兵棋推演模組是一套多方商務沙盤推演與決策訓練引擎，涵蓋商戰對決、併購談判、供應鏈博弈、反壟斷調查與危機公關等情境。

設計原則：

1. **策略不可知**：底線成本、讓步階梯、施壓籌碼等敏感輸入在客戶端加密，以全同態加密（FHE）密文參與運算；運算節點不接觸明文。
2. **行動不可否認**：每次出價、施壓、釋放信號與查看動作皆生成數位簽章，形成可回放的因果鏈，供覆盤與教學使用。
3. **偽匿名互動**：參與者可在不揭露現實身分的前提下進行推演。

## 架構概觀

    [ AllView Ecosystem: allview.today ]
           ├── Presale Showcase Repo: allview-market-simulation-presale
           └── Functional Engine Repo: allview-market-simulation-app
                   ├── Interactive Wargame Sandbox (Canvas/WebGL)
                   ├── FHE Strategy Collision Engine (OpenFHE / TFHE-rs)
                   ├── Verifiable Audit Ledger (Merkle-tree Signed Action Chain)
                   └── AI Scenario & Opponent Agent Runtime

FHE 核心來源（本倉自行整合 OpenFHE／TFHE-rs，或由 AEGIS `aegis.expert` 協作提供）[待確認]；如屬協作，不改變本產品歸屬 AllView。

## 功能模組

| 代號 | 模組 | 範圍 |
| :--- | :--- | :--- |
| MOD-01 | Simulation Modes | 回合制／即時制；1v1、多方聯盟、監管方加入；自我對自我、AI+真人、匿名多方配對 |
| MOD-02 | Sandbox Board | 戰略大盤、供應鏈拓撲、現金流曲線；What-if 分支樹 |
| MOD-03 | Negotiation Core | ZOPA 探索、施壓倒數、BATNA、資訊不對稱欺敵 |
| MOD-04 | FHE Strategy Engine | 多方密文交集、成本區間重疊比對、勝率估算（不接觸明文） |
| MOD-05 | Evidence Chain | 雙向會話棘輪、不可竄改操作簽章（Signed Action Records） |
| MOD-06 | AI Agent Runtime | 本地或受控模型推理；激進／保守／欺敵風格對手；訓練模式策略熱度圖 |
| MOD-07 | AAR & Case Studio | 時間軸覆盤、關鍵節點標記、敏感資料脫敏匯出教學個案 |
| MOD-08 | RBAC & Mode Guard | 教練／觀察員／選手；訓練模式（允許提示）與實戰模式（屏蔽提示、防作弊） |

## 密碼學邊界

    [Client] (1) 戰略明文輸入 → (2) 以 Session Context Key 加密為 FHE 密文
       ▼
    [Untrusted Compute Node] (3) 接收各方密文（BFV/BGV 整數比較；CKKS 風險機率矩陣）
                              (4) 密文碰撞（是否成交？施壓是否越過門檻？）
                              (5) 輸出密文結果，或僅揭露必要布林狀態（成交／未成交／臨界警報）
       ▼
    [Audit Log] (6) 動作 Hash + 簽章寫入 Merkle Action Block

紅線：

- **禁止明文上傳**：BATNA、真實出價邊界等底牌不得以明文或僅以 TLS 加密送達服務端記憶體。
- **固定電路**：FHE 運算僅限預先定義的比較器、多項式評分與加權矩陣；自然語言對話生成一律走隔離的受控推論，不做全量 FHE NLP。

效能、延遲與可支援人數：[待確認]，以 `tests/crypto-bench` 實測結果為準後再對外發布。

## 目錄結構

    allview-market-simulation-app/
    ├── .github/ (CODEOWNERS, PULL_REQUEST_TEMPLATE.md, workflows/)
    ├── docs/
    │   ├── ARCHITECTURE.md
    │   ├── REQUIREMENTS.md
    │   ├── QA-ACCEPTANCE.md
    │   ├── FHE-INTERFACE-SPEC.md
    │   └── THREAT-MODEL.md
    ├── packages/
    │   ├── client-web/
    │   ├── core-simulation-engine/
    │   ├── crypto-fhe-adapter/
    │   ├── ledger-evidence-chain/
    │   └── ai-agent-runtime/
    ├── tests/ (e2e/, crypto-bench/, unit/)
    ├── package.json
    └── README.md

## 本地開發

前置：Node.js >= 20.x（建議 pnpm >= 9.x）、Rust >= 1.78、CMake & Clang（重新編譯 OpenFHE/TFHE-rs 綁定時）、Docker >= 24.x。

    git clone https://github.com/allview-today/allview-market-simulation-app.git
    cd allview-market-simulation-app
    pnpm install
    pnpm run build:crypto
    pnpm run dev

瀏覽 `http://localhost:3000` 進入除錯模式。

## QA 閘門

依 PMO 七道閘門管控（各閘門目前達成狀態 [待確認]）：

- Gate 0 Scope Ready：需求具 FR 編號，界定加密／非加密範圍
- Gate 1 Design Ready：FHE 電路深度評估、簽章流程圖
- Gate 2 Build Ready：Lint、TypeScript 檢查、單元測試覆蓋率 >= 80%
- Gate 3 Integration Ready：模擬引擎與 FHE 配對服務整合
- Gate 4 Security Ready：抗側信道與重放攻擊驗收、無硬編碼金鑰
- Gate 5 Release Ready：多人推演壓測，延遲符合 SLA 門檻（門檻數值 [待確認]）
- Gate 6 Post-release：灰度上線與回滾驗證

## 協作規範

- 認領帶 `status: ready-for-dev` 與 `bounty` 標籤的 Issue
- 分支：`feat/FR-[編號]-[描述]`、`fix/BUG-[編號]-[描述]`
- Commit 遵守 Conventional Commits
- PR 需關聯 Issue、附本地測試紀錄，並經至少一位 Code Owner 核准

## 角色信箱

- Dev Lead：`dev-allview-market-simulation-app@allview.today`
- Collaborator Team：`collab-allview-market-simulation-app@allview.today`
- QA Lead：`qa-allview-market-simulation-app@allview.today`
- Repo Admin / PMO：`admin-allview-market-simulation-app@allview.today`
- 資安漏洞通報：`github-security@wonderland.center`（[待確認] 是否為正確窗口）

## 授權與免責

- 授權方式（閉源或指定開放授權）[待確認]，以 `LICENSE` 為準。
- 本系統所提供之 AI 提示、勝率估算與策略建議僅供商務決策訓練與教育參考，不構成任何正式法律、投資或併購操作之保證依據。
```

---

## 9. 本次建議人工審核重點

1. **正式名稱與品牌關係**：「VeilProof（隱證）」是本模組名稱，還是 AllView 既有產品品牌？README 稱本模組基於「VeilProof 原有」的 E2EE／偽匿名／證據鏈底座擴展，與 FHE Social 的關係需釐清，避免兩條線被視為同一產品。
2. **PMO 代碼與產品線編號**：README 未提供 `C3-AV-xxx-F`／`C2-AV-xxx` 代碼。
3. **比較級與徽章**：同意不對外使用「Signal 級」「極限商戰」「密碼學級」「杜絕」等措辭，以及 `CI/CD Passing`、`Security Audit Ready` 徽章；是否有第三方稽核或測試報告可支撐任何安全宣稱。
4. **即時制與效能**：即時制在 FHE 下的延遲、可支援人數、Gate 5 SLA 門檻數值，目前全無數據。
5. **FHE 核心來源**：自行整合 OpenFHE／TFHE-rs，或由 AEGIS 協作提供；若為後者，需在文件標示協作關係。
6. **資安窗口**：`github-security@wonderland.center` 是否正確（跨事業體網域）。
7. **法律效力與免責**：證據鏈能否在仲裁場景使用；預售文案已避免「可作為法律證據」。
8. **商業條件**：銷售模式、價格、交期、授權條款本次未提供，草稿留空。
9. **本文件狀態**：草稿 v0.2，**尚未最終確認**。
