# VeilProof
C2-AV-MWS 隱證 VeilProof 商場沙盤推演與文化兵推模擬系統 for 併購顧問、跨國公關、戰略規劃
# VeilProof (隱證) 商務兵棋推演／沙盤推演模擬模組 (`allview-market-simulation-app`)

[![CI/CD Pipeline](https://img.shields.io/badge/CI%2FCD-Passing-brightgreen?style=flat-square)](https://github.com/allview-today/allview-market-simulation-app/actions)
[![Security Audit](https://img.shields.io/badge/Security-Audit%20Ready-blue?style=flat-square)](./SECURITY.md)
[![FHE Engine](https://img.shields.io/badge/Crypto-OpenFHE%20%7C%20TFHE--rs-orange?style=flat-square)](https://openfhe.org)
[![QA Gates](https://img.shields.io/badge/QA%20Gates-Gate%200%20to%20Gate%206-teal?style=flat-square)](./QA-ACCEPTANCE.md)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen?style=flat-square)](./CONTRIBUTING.md)

---

## 1. 專案定位與系統架構脈絡 (Overview & Ecosystem)

**VeilProof 商務兵棋推演／沙盤推演模擬模組**（代號：`allview-market-simulation-app`）是 AllView (`allview.today`) 數位傳播與互動技術生態矩陣下的核心第三類功能性技術儲存庫（Functional Technology Repository）。

本系統基於 VeilProof 原有的「Consumer-grade 易用性 + Signal 級端對端加密 + 偽匿名身分鏈 + 不可否認證據鏈」技術底座，進一步擴展為面向**商戰對決、併購談判、供應鏈博弈、反壟斷調查與危機公關**的多方沙盤推演與決策訓練引擎。

```
[ AllView Ecosystem: allview.today ]
       │
       ├── Presale Showcase Repo: allview-market-simulation-presale (Landing / Marketing)
       └── Functional Engine Repo: allview-market-simulation-app (THIS REPOSITORY)
               ├── Interactive Wargame Sandbox (Canvas/WebGL)
               ├── FHE Strategy Collision Engine (OpenFHE / TFHE-rs)
               ├── Verifiable Audit Ledger (Merkle-tree Signed Action Chain)
               └── AI Scenario & Opponent Agent Runtime
```

### 核心設計哲學
1. **策略不可知（Zero-Knowledge of Tactics）**：投入系統的底線成本、讓步階梯、施壓底牌全程處於全同態加密（FHE）狀態，雲端主機與演算法節點僅在密文上碰撞計算，杜絕運營方或任何對手偷窺底牌。
2. **行動不可否認（Non-Repudiable Evidence）**：每次出價、施壓、釋放假信號、查看對手動作，皆生成不可否認數位簽章，構建事後覆盤、法律教學與仲裁的密碼學級因果鏈。
3. **完全偽匿名互動（Pseudonymous Engagement）**：推演雙方（或多方）在零現實身分洩露的前提下進行極限商戰心理攻防。

---

## 2. 功能矩陣與模組架構 (Functional Architecture)

```
allview-market-simulation-app/
├── [A] Mode Controller       ── 自我對自我 / AI+真人 / 完全匿名多方配對
├── [B] Interactive Sandbox   ── 視覺化戰略/戰術沙盤、單位資源調配、時間軸分叉
├── [C] Negotiation Engine    ── 結構化議價、心理施壓模組、假信號投放與欺敵
├── [D] FHE Compute Kernel    ── 密文勝率預估、密文敏感度碰撞、可調粒度揭露
├── [E] Verifiable Audit      ── 動作數位簽章、Merkle 狀態鏈、授權密鑰揭露
├── [F] AI Agent Orchestrator ── 自適應風格對手（激進/保守/欺騙）、即時戰術雷達
├── [G] After-Action Review   ── 互動時間軸覆盤、教學案例脫敏匯出、社群論壇整合
└── [H] Governance & Security ── 角色階層授權（教練/觀察員/選手）、實戰與訓練模式
```

### 核心功能子模組說明

| 模組代號 | 模組名稱 | 關鍵責任與開發範圍 |
| :--- | :--- | :--- |
| **MOD-01** | **Simulation Modes** | 支援回合制（Turn-based）與即時制（Real-time）；動態配對（1v1、多方聯盟、監管方加入）。 |
| **MOD-02** | **Sandbox Board** | 多層級視圖（戰略大盤、供應鏈拓撲、現金流曲線）；分支樹模擬（Branching / "What-if"）。 |
| **MOD-03** | **Negotiation Core** | 結構化談判協議（ZOPA 探索、施壓倒數計時器、替代方案 BATNA 威脅、資訊不對稱欺敵）。 |
| **MOD-04** | **FHE Strategy Engine** | 呼叫同態運算核心進行多方密文交集、成本區間重疊比對、勝率估算（不接觸明文）。 |
| **MOD-05** | **Evidence Chain** | 整合 Signal Protocol 級雙向會話棘輪與不可竄改操作簽章（Signed Action Records）。 |
| **MOD-06** | **AI Agent Runtime** | 本地或受控模型推理，扮演具備詐術與抗壓特性的虛擬對手，提供即時策略熱度圖提示。 |
| **MOD-07** | **AAR & Case Studio** | 覆盤編輯器，提供關鍵決策節點打標、敏感資料脫敏演算法，轉化為教學個案。 |
| **MOD-08** | **RBAC & Mode Guard** | 「訓練模式」（允許 AI 雷達外掛提示）與「實戰模式」（完全屏蔽提示、強制防作弊檢查）。 |

---

## 3. FHE 與密碼學邊界規範 (Cryptographic Boundaries)

為確保在工程實作時兼顧效能與安全性，所有參與者**嚴禁隨意擴大運算邊界**。請嚴格遵守以下密碼分層原則：

```
[客戶端 (Client)]
   │
   ├── (1) 戰略明文輸入 (底線利潤、預算上限、公關籌碼)
   ├── (2) 本地客戶端加密 (以 Session Context Key 加密成 FHE Ciphertext)
   │
   ▼
[推演運算節點 (Untrusted Compute Node)]
   │
   ├── (3) 接收各方 FHE 密文 (BFV/BGV 處理整數比較，CKKS 處理風險機率矩陣)
   ├── (4) 密文碰撞 (不解密判斷：是否成交？施壓權重是否打破心理門檻？)
   ├── (5) 輸出密文結果或僅揭露必要布林狀態 (成交/未成交/臨界警報)
   │
   ▼
[不可否認日誌 (Audit Log)]
   │
   └── (6) 動作 Hash + 簽章寫入 Merkle Action Block
```

* **嚴格紅線**：
  * **禁止明文上傳**：所有底牌資料（如 BATNA 數字、真實出價邊界）嚴禁以明文或僅以傳輸層 TLS 加密送達服務端記憶體。
  * **固定電路（Bounded Circuits）**：FHE 運算僅限於預先定義好的比較器、多項式評分與加權矩陣；大型自然語言對話生成（NLP/LLM）一律透過隔離之受控推論執行，不得強行做全量 FHE NLP。

---

## 4. 目錄結構 (Directory Layout)

```bash
allview-market-simulation-app/
├── .github/
│   ├── CODEOWNERS                  # 模組審核負責人對應
│   ├── PULL_REQUEST_TEMPLATE.md    # PR 統一格式
│   └── workflows/                  # CI/CD (Lint, Unit Test, Crypto Benchmark)
├── docs/
│   ├── ARCHITECTURE.md             # 系統深層架構設計圖
│   ├── REQUIREMENTS.md             # 功能與非功能性需求清單 (FR-xxx / NFR-xxx)
│   ├── QA-ACCEPTANCE.md            # QA 測試驗收規範與測試案例 (TC-xxx)
│   ├── FHE-INTERFACE-SPEC.md       # 同態加密介面與參數規格書
│   └── THREAT-MODEL.md             # 威脅模型與安全假定
├── packages/
│   ├── client-web/                 # 視覺化推演沙盤前端 (React / Three.js / Canvas)
│   ├── core-simulation-engine/     # 推演狀態機、回合排程與談判協議控制器
│   ├── crypto-fhe-adapter/         # FHE 核心橋接模組 (C++/Rust FFI, OpenFHE/TFHE)
│   ├── ledger-evidence-chain/      # 動作簽章、Merkle 樹聚合與回放驗證器
│   └── ai-agent-runtime/           # AI 對手模擬與提示推論驅動 (Local/API Adapter)
├── tests/
│   ├── e2e/                        # 多角色模擬對抗端到端測試
│   ├── crypto-bench/               # FHE 密文延遲、記憶體開銷與噪聲基準測試
│   └── unit/                       # 各模組單元測試
├── package.json
└── README.md                       # 本文件
```

---

## 5. 快速上手與本地開發 (Quick Start)

### 前置環境要求
* **Node.js**: `>= 20.x` (建議使用 `pnpm >= 9.x`)
* **Rust**: `>= 1.78` (用於編譯 `crypto-fhe-adapter`)
* **CMake & Clang**: (若需重新編譯底層 OpenFHE/TFHE-rs 綁定)
* **Docker**: `>= 24.x` (用於快速啟動本機端模擬節點與測試資料庫)

### 安裝與啟動步驟

```bash
# 1. 複製儲存庫
git clone https://github.com/allview-today/allview-market-simulation-app.git
cd allview-market-simulation-app

# 2. 安裝相依套件
pnpm install

# 3. 編譯 FHE 加密橋接層 (Debug 模式)
pnpm run build:crypto

# 4. 啟動本機模擬推演沙盒環境
pnpm run dev
```

開啟瀏覽器造訪 `http://localhost:3000`，即可進入沙盤推演除錯模式。

---

## 6. QA 驗收閘門與品質要求 (QA Acceptance Gates)

本專案納入 PMO 全域統一控管之 **七道 QA 閘門** 機制。任何功能分支合併（Merge）前必須達到相應閘門標準：

```
Gate 0: Scope Ready       ── 需求具有明確 FR 編號，明確界定加密與非加密範圍
Gate 1: Design Ready      ── 具備 FHE 電路深度評估與不可否認證據簽章流程圖
Gate 2: Build Ready       ── 程式碼通過 Lint、TypeScript 檢查、單元測試覆蓋率 >= 80%
Gate 3: Integration Ready ── 模擬引擎與 FHE 加密配對服務端整合成功
Gate 4: Security Ready    ── 通過抗側信道與重放攻擊驗收，無硬編碼金鑰
Gate 5: Release Ready     ── 完成端到端多人推演壓測，延遲符合 SLA 門檻
Gate 6: Post-release      ── 支援灰度上線與完整回滾（Rollback）驗證
```

詳細測試項目對照請參閱 [`docs/QA-ACCEPTANCE.md`](./docs/QA-ACCEPTANCE.md)。

---

## 7. 協作規範與群眾發包指南 (Contributing & Crowdsourcing)

我們歡迎社群開發者、密碼學研究員與商戰模擬愛好者共同參與。請依循以下協同規則：

1. **認領任務**：請在 GitHub Issues 中尋找帶有 `status: ready-for-dev` 與 `bounty` 標籤的 Issue，留言認領後由專案負責人指派。
2. **分支命名**：
   * 功能：`feat/FR-[編號]-[簡短英文描述]` (例如：`feat/FR-004-fhe-zopa-check`)
   * 修復：`fix/BUG-[編號]-[簡短英文描述]`
3. **Commit 規範**：必須遵守 [Conventional Commits](https://www.conventionalcommits.org/) 格式。
4. **Pull Request 流程**：
   * PR 必須自動關聯對應的 Issue（如 `Fixes #42`）。
   * 必須附上本地測試通過之日誌或截圖。
   * 需通過至少一位 Code Owner（依據 `.github/CODEOWNERS`）的審核核准。

---

## 8. 通訊與團隊責任分工 (Team & Contact Aliases)

依據 PMO 控制表規範，本 Repo 設有專屬角色郵件別名（Aliases），請勿將私有個人聯絡方式提交至版本控制：

* **Dev Lead**: `dev-allview-market-simulation-app@allview.today`
* **Collaborator Team**: `collab-allview-market-simulation-app@allview.today`
* **QA Lead**: `qa-allview-market-simulation-app@allview.today`
* **Repo Admin / PMO**: `admin-allview-market-simulation-app@allview.today`
* **資安漏洞通報**: `github-security@wonderland.center`

---

## 9. 授權與責任聲明 (License & Disclaimer)

* 本專案原始碼依據組織治理規範進行閉源授權或指定開放授權，請參閱本 Repo 之 [`LICENSE`](./LICENSE) 檔案。
* **免責宣告**：本沙盤推演系統所提供之 AI 提示、勝率估算與策略建議僅供商務決策訓練與教育參考，不構成任何正式法律、投資或並購操作之保證依據。
