# N8N 練習專案

這是一個用於學習和練習 n8n 工作流自動化平台的專案。

## 項目說明

n8n 是一個強大的工作流自動化平台，可以幫助我們：
- 連接不同的服務和 API
- 自動化重複性工作
- 建立自定義的工作流程
- 處理數據轉換和整合

## 快速開始

1. 克隆專案：
```bash
git clone https://github.com/yenhunghuang/n8n-practice.git
cd n8n-practice
```

2. 使用 Docker Compose 啟動：
```bash
docker-compose up -d
```

3. 訪問 n8n：
- 打開瀏覽器訪問：http://localhost:5678
- 使用預設帳號：admin
- 使用預設密碼：admin123

## 目錄結構

```
.
├── README.md
├── docker-compose.yml    # Docker 配置文件
├── workflows/           # n8n 工作流程範例
└── docs/               # 文檔和說明
```

## 注意事項

- 請修改預設的用戶名和密碼
- 在生產環境中建議使用 HTTPS
- 定期備份你的工作流程

## 貢獻指南

歡迎提交 Pull Request 或創建 Issue 來改進這個專案。

## 授權

MIT License