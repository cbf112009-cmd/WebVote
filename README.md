1.	UniGov: 全方位去中心化治理與行為激勵引擎
UniGov (Universal Governance) 是一個整合了多種計票模型、行為激勵機制與遊戲化體驗的 Web3 治理中樞。
📖 專案願景 (Vision)
傳統組織決策常面臨「資訊黑箱」與「參與度低落」的痛點。UniGov 透過區塊鏈技術確保數據的不可竄改性，並透過聲譽值 (Reputation) 與稱號收集 (Achievements) 系統，將枯燥的投票行為轉化為具備養成感的治理生態。
________________________________________
🛠️ 核心實作功能清單 (31 項)
一、 大廳、導覽與身分 (UX & Identity)
2.	獨立大廳引導頁 (Onboarding)：1-2-3 步驟拆解 Web3 流程，引導新手。
3.	模式百科頁面 (Encyclopedia)：完整中文化說明五大模式（含數學公式）。
4.	狀態分類列表：動態標籤顯示「進行中」或「已截止」案。
5.	個人身分修改系統：使用者可隨時更新治理暱稱與頭像。
6.	錢包斷開機制：提供斷開連線功能，徹底清除介面暫存。
7.	自動網路偵測與切換：強制要求並引導切換至 Sepolia 測試網。
8.	使用者儀表板 (Dashboard)：即時顯示個人 Rep、等級與徽章。
9.	全域關鍵字搜尋：支援標題、UID、地址的即時過濾。
二、 發起端：自動化與管理 (Creator Suite)
9.	候選人 UID 自動補全：系統對空白欄位自動生成隨機唯一的 CAND-XXXX。
10.	發起人編輯權限 (Edit Lock)：[安全機制] 判斷若票數為 0，發起人具備修改權。
11.	動態模式表單：選單自動切換專屬參數欄位（如點數設定、池金設定）。
12.	時限與權限參數：支援分鐘制計時與黑白名單架構預留。
13.	IPFS 內容存儲支援：支援將大型 asset hash 存於鏈上，優化存儲成本。
三、 模式專屬設定 (Mode Config)
14.	平方投票 (QV) 參數：設定初始點數（預設 100）與加權係數。
15.	平方募資 (QF) 獎勵池：設定配對金總額與算法邏輯。
16.	排序投票 (Ranked) 設定：與合約 Enum 模式 3 同步。
17.	權重投票 (Weighted) 設定：支援綁定外部 ERC-20 代幣合約地址。
四、 投票端互動 (Voter Experience)
18.	QV 點數即時計數器：動態換算 $Cost = Votes^2$。
19.	QF 獎勵模擬引擎：輸入金額時即時試算預計能帶動的「配對獎勵金」。
20.	排序拖曳控制器：整合 SortableJS 實作直覺的順序調整介面。
21.	權重即時查詢：自動調用錢包 Provider 抓取目前帳戶權重。
五、 執行、安全與數據 (Execution & Data)
22.	合約交互防呆檢查：提交交易前的權限檢驗與 Toast 提醒。
23.	交易狀態追蹤：實作 Loading、Tx Hash 分享與 Confetti 成功特效。
24.	數據看板視覺化：整合 Chart.js 展示全網治理趨勢。
25.	鏈上審計日誌：即時顯示各項操作的 Tx Hash，確保數據具備 Traceability。
六、 治理遊戲化與娛樂 (Gamification)
26.	治理領袖排行榜 (Leaderboard)：展示全網信譽度前三名大師。
27.	每日治理簽到獎勵 (Daily Check-in)：點擊領取 Rep，增加使用者黏性。
28.	動態等級進度系統 (Leveling)：根據 Rep 成長自動填充視覺進度條。
29.	幸運治理轉盤 2.0 (Lucky Wheel)：抽選今日運勢與純娛樂性質稱號。
30.	趣味稱號系統 (Flavor Titles)：如「治理小博士」、「共識大師」等稱號。
31.	稱號成就收藏室 (Achievement Room)：個人頁面稱號牆，永久保存所有抽中的歷史榮譽。
________________________________________
🏛️ 治理等級體系 (Leveling Standards)
系統將參與度量化為聲譽值（Rep），並自動劃分等級：
等級名稱	Rep 門檻	視覺稱號	描述
🌱 治理萌芽	0 - 50	Novice	初入治理殿堂的探索者
🛡️ 治理執法者	51 - 150	Enforcer	積極參與共識的維護者
⚖️ 中堅仲裁官	151 - 300	Arbitrator	具備決策經驗的核心成員
👑 治理傳奇	301 - 500	Legend	社群公認的治理領袖
🌌 永恆守護者	501+	Guardian	治理體系的頂端存在
________________________________________
🔬 技術架構 (MIS Perspective)
1. 開發工具鏈
•	Smart Contract: Solidity 0.8.18 (Remix IDE)
•	Frontend: HTML5, CSS3 (Glassmorphism), Vanilla JavaScript
•	Web3 Library: Ethers.js v5.7
•	Gamification: Canvas-confetti, SortableJS, LocalStorage (Persistence)
•	Analytics: Chart.js
2. 治理模型與數學 (Knowledge Center)
•	平方投票 (Quadratic Voting):
藉由增加投票成本來保護少數族群的意見。
•	平方募資 (Quadratic Funding):
$\text{Reward} = (\sum \sqrt{c_i})^2$
重視貢獻人數而非總額，用於公平分配公共財資源。
3. 防黑箱與審計機制
•	持久化存儲 (Persistence): 即使重新連線，使用者的 localStorage 數據將與鏈上地址綁定。
•	無人投票編輯鎖 (The First-Vote Lock): 當議案 totalVotes > 0 時，發起人的編輯面板將永久失效，確保後設資料不被惡意修改。
________________________________________
🚀 快速開始 (Deployment Guide)
1.	部署合約: 於 Remix IDE 部署 UniGov.sol 至 Sepolia 測試網。
2.	配置地址: 將部署後的 Contract Address 填入 index.html 的 CONTRACT_ADDR 常數。
3.	複製 ABI: 將編譯後的 JSON 格式 ABI 貼入 const ABI 變數。
UniGov - 讓每一份共識都具備透明度與參與的喜悅。
5.	運行: 使用瀏覽器開啟 index.html，連接 MetaMask 即可啟動。
________________________________________UniGov - 讓每一份共識都具備透明度與參與的喜悅
