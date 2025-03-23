# 天氣提醒工作流

這個工作流程會定期檢查台北的天氣狀況，並通過 Telegram 發送提醒。

## 功能特點

- 每 3 小時自動檢查一次台北天氣
- 使用 OpenWeatherMap API 獲取實時天氣數據
- 當溫度超過 26°C 時發送高溫提醒
- 通過 Telegram Bot 發送通知

## 前置需求

1. OpenWeatherMap API Key
   - 註冊：https://openweathermap.org/
   - 獲取 API Key

2. Telegram Bot
   - 使用 @BotFather 創建機器人
   - 獲取 Bot Token
   - 使用 @RawDataBot 獲取 Chat ID

## 工作流節點說明

1. Schedule Trigger
   - 設置為每 3 小時觸發一次

2. Edit Fields (API Key)
   - 設置 OpenWeatherMap API Key

3. HTTP Request
   - 調用 OpenWeatherMap API
   - 獲取台北天氣數據

4. IF
   - 檢查溫度是否超過 26°C
   - 根據條件分流

5. High Temp / Low Temp
   - 根據溫度生成不同的提醒消息

6. Telegram
   - 發送提醒消息到指定的 Telegram 聊天

## 使用方法

1. 導入工作流 JSON 文件
2. 設置必要的認證信息：
   - OpenWeatherMap API Key
   - Telegram Bot Token
   - Telegram Chat ID
3. 激活工作流

## 注意事項

- API Key 和 Bot Token 請妥善保管，不要分享給他人
- 可以根據需要調整溫度閾值和檢查頻率
- 建議先使用測試功能確認設置正確