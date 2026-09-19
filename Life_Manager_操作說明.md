# Life Manager 操作說明

## 日常使用

1. 打開 Vercel 網站。
2. 使用 Email + Password 登入。
3. 登入後可以新增、編輯、刪除：
   - 專案
   - 任務
   - 約會
4. 勾選任務或約會完成後，資料會同步到 Supabase。
5. 手機和電腦登入同一個帳號，會看到同一份資料。

## 帳號與資料規則

- 每個 Email 帳號只看得到自己的資料。
- 其他人用自己的 Email 註冊後，會看到自己的空資料，不會看到你的資料。
- 第一次登入時，舊資料已經被認領到你的帳號。
- 不要隨便按「重設範例資料」，它會清空目前登入帳號的資料。

## 目前專案位置

- 桌面網站檔案：
  `C:\Users\user\Desktop\Life_Manager\index.html`

- GitHub repo：
  `https://github.com/tienhsin0618/Life_Manager`

- WSL 本機 repo：
  `/home/tien/Life_Manager_github`

- Supabase 資料表：
  - `life_projects`
  - `life_tasks`
  - `life_events`

## 修改網站流程

建議流程：

1. 修改 `/home/tien/Life_Manager_github/index.html`
2. 檢查語法。
3. commit。
4. push 到 GitHub main branch。
5. Vercel 會從 GitHub 自動重新部署。
6. 必要時再把 GitHub 版本覆蓋回桌面 `index.html`。

## 下次開新對話要給 Codex 的提示

可以直接貼這段：

```text
請接續 Life_Manager 專案。
桌面檔案：C:\Users\user\Desktop\Life_Manager\index.html
GitHub repo：https://github.com/tienhsin0618/Life_Manager
WSL repo：/home/tien/Life_Manager_github
目前已串 Supabase Email + Password 登入，資料表是 life_projects、life_tasks、life_events。
請先讀取現有檔案，再依照我的需求修改 UI 或功能，最後同步到 GitHub / Vercel。
```

## Supabase 注意事項

- 前端只能放 `anon / publishable key`。
- 不要把 `service_role`、`sb_secret_...` 放進 `index.html`、GitHub 或 Vercel 前端環境。
- 如果寄驗證信出現 `email rate limit exceeded`，代表短時間寄太多信，等 30-60 分鐘再試。
- 如果只是個人使用，可以在 Supabase 關掉 Email confirmation；多人正式使用再考慮接 Resend。

## 常見問題

### 手機和電腦字體不同

目前已改成全站使用 `Noto Sans TC`，正常情況下手機和電腦會更一致。

### 登入後資料空白

先不要新增或重設資料。檢查 Supabase 三張表的 `user_id` 是否正確歸到目前登入帳號。

### Vercel 沒更新

先確認 GitHub main branch 有最新 commit，再到 Vercel 看 deployment 是否完成。必要時手動 redeploy。

