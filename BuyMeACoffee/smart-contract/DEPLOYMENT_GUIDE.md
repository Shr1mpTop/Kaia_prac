运行部署命令：
```bash
npx hardhat run scripts/deploy.js --network kairos
```

部署成功后会显示：
```
BuyMeACoffee Contract Address 0x...
```

**保存这个合约地址！**

### 4️⃣ 配置 withdraw.js

部署成功后，打开 `scripts/withdraw.js`，填写：

```javascript
// 粘贴部署时获得的合约地址
const buyMeACoffeAddress = "0x...";

// 粘贴你的钱包地址 (部署者地址)
const deployerAddress = "0x...";
```

### 5️⃣ 测试提款功能

当合约中有资金时，运行：
```bash
npx hardhat run scripts/withdraw.js --network kairos
```

---

## 📁 项目文件结构

```
smart-contract/
├── contracts/
│   └── BuyMeACoffee.sol      ✅ 智能合约
├── scripts/
│   ├── bmc-coffee.js         ✅ 本地测试脚本
│   ├── deploy.js             ✅ 部署脚本
│   └── withdraw.js           ✅ 提款脚本 (需配置)
├── .env                       ✅ 环境变量 (需配置)
├── hardhat.config.js          ✅ Hardhat 配置
└── package.json
```

## 🔍 验证部署

在 KaiaScan 浏览器验证：
https://kairos.kaiascan.io/

搜索你的合约地址查看详情。

---

## ⚠️ 注意事项

1. **.env 文件**: 已添加到 .gitignore，不会上传到 GitHub
2. **私钥安全**: 永远不要分享或上传私钥
3. **测试网**: 确保使用 Kairos 测试网，不是主网
4. **Gas 费**: 确保钱包有足够的 KAIA 支付 gas 费

---

## 📝 快速命令参考

```bash
# 本地测试
npx hardhat run scripts/bmc-coffee.js

# 部署到 Kairos 测试网
npx hardhat run scripts/deploy.js --network kairos

# 提取合约资金
npx hardhat run scripts/withdraw.js --network kairos

# 验证合约
npx hardhat verify --network kairos <CONTRACT_ADDRESS>
```

---

Good luck! 🚀
