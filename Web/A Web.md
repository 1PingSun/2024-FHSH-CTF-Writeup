# A Web

Author: 孫逸平

Date: 2024-06-07

Link: https://ctfd.fhh4ck3rs.taipei/challenges#A%20Web-19

## 題目說明

Just a WEB, nothing else..

> Author: xiunG

我認真的說...就是一個 web，沒有其他的了..

## Write-up

1. 執行偵查，打開路徑 `/robots.txt`，找到第一段 flag：`FhCTF{1aSy_t0_f0`。
2. 點擊主頁的 Login 字樣，看到登入介面，使用 SQLi 嘗試，帳號為：`' OR 1=1-- -`，密碼則隨意輸入，即成功登入得到第二段 flag：`UnD_A_f1AG_c`。
3. 查看 Cookie 發現 `isAdmin` 的值為：`RmFsc2U=`，經過 base64 解碼後得到 `False` 字串。
4. 利用 base64 將 `True` 編碼後得到：`VHJ1ZQ==`，並將 Cookie 的 `isAdmin` 值修改為：`VHJ1ZQ==` 後重新整理網頁，就看到第三段 flag：`An_u_f1ND_1T}`。
5. 將三段 flag 組合後提交：`FhCTF{1aSy_t0_f0UnD_A_f1AG_cAn_u_f1ND_1T}`。
