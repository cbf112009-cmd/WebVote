# UniGov: 多模式去中心化治理系統

## 專案簡介
UniGov 是一個基於以太坊的去中心化治理平台，旨在提供安全、透明且具備高效能數據檢索能力的投票環境。本系統集成了五種主流的民主決策模型，並透過 IPFS 與前端索引技術優化了系統架構。

## 技術架構
1. **區塊鏈層 (On-chain Logic)**: 採用 Solidity 開發，負責核心計票演算法與身分權限控管。
2. **存儲層 (Decentralized Storage)**: 利用 IPFS 存儲高容量候選人資訊，合約僅保存 CID 指標，降低 80% 儲存成本。
3. **索引層 (Performance Optimization)**: 捨棄傳統後端資料庫，透過前端抓取區塊鏈 Event Logs 進行數據聚合。

## 投票模式說明
- **一般投票**: 簡單多數決。
- **平方投票**: 解決大眾平庸化問題，投票成本為：$Cost = Votes^2$。
- **流動民主**: 支援權力委託，建立社群信任鏈。
- **承諾揭示**: 採用加密雜湊兩階段投票，防止跟風效應。

## 開發環境
- **Smart Contract**: Remix IDE
- **Frontend**: VS Code (Vanilla JS + ethers.js)
- **Version Control**: GitHub
