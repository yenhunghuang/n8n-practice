# 天氣提醒工作流

這個工作流展示了如何使用 n8n 創建一個自動天氣提醒系統。它會定期檢查台北的天氣，當溫度超過設定閾值時發出提醒。

## 功能特點
- 每 3 小時自動檢查一次天氣
- 使用 OpenWeatherMap API 獲取即時天氣數據
- 根據溫度高低發送不同的提醒消息
- 支持自定義溫度閾值

## 前置需求
1. 註冊 [OpenWeatherMap](https://openweathermap.org/) 帳號
2. 獲取 API Key（免費版即可）

## 使用步驟

### 1. 導入工作流
1. 在 n8n 介面中點擊「工作流」
2. 選擇「導入」
3. 上傳 `02-weather-alert.json` 文件

### 2. 配置 API Key
1. 找到「Set API Key」節點
2. 將你的 OpenWeatherMap API Key 填入 `apiKey` 欄位
3. 保存更改

### 3. 自定義設置
- **檢查頻率**：在 Schedule Trigger 節點中修改
- **溫度閾值**：在 Check Temperature 節點中修改（默認 30°C）
- **城市**：在 Get Weather 節點的 URL 中修改 `q=taipei` 參數

### 4. 添加通知（可選）
你可以在 High Temp Alert 和 Normal Temp 節點後添加：
- Slack 通知
- Email 通知
- Discord 通知
- 其他通知方式

## 工作流說明

### 節點功能
1. **Schedule Trigger**：定時觸發工作流
2. **Set API Key**：設置 API 密鑰
3. **Get Weather**：調用天氣 API
4. **Check Temperature**：檢查溫度條件
5. **High Temp Alert**：生成高溫提醒消息
6. **Normal Temp**：生成普通天氣消息

### 數據流
1. 觸發器每 3 小時執行一次
2. 讀取 API Key
3. 獲取台北天氣數據
4. 檢查溫度是否超過閾值
5. 根據條件生成對應消息

## 進階改進建議
1. 添加濕度檢查
2. 增加天氣預報功能
3. 支持多個城市
4. 添加極端天氣警報
5. 整合其他天氣 API

## 故障排除
- 確保 API Key 正確
- 檢查網絡連接
- 確認城市名稱拼寫正確
- 查看 n8n 執行日誌

## 參考資源
- [OpenWeatherMap API 文檔](https://openweathermap.org/api)
- [n8n HTTP Request 節點文檔](https://docs.n8n.io/nodes/n8n-nodes-base.httpRequest/)
- [n8n IF 節點文檔](https://docs.n8n.io/nodes/n8n-nodes-base.if/)