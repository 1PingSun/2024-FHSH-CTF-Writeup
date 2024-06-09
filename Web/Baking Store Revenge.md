# Baking Store Revenge

Author: 孫逸平

Date: 2024-06-08

Link: https://ctfd.fhh4ck3rs.taipei/challenges#Baking%20Store%20Revenge-34

## 題目說明

復仇，復仇，最後的復仇

> Author: CXPh03n1x

可以見得，已經出題目出到瘋了...

> **Hint:**
>
> 跟你想的不太一樣啦～
> 別老是 Injection，看看其他的漏洞吧！

## Write-up

1. 發現頁面中的登入鍵，註冊一個帳號後發現連結為：`https://baking-revenge.fhh4ck3rs.taipei/users/65537`。
2. 猜測此為 IDOR 之漏洞，將 `65537` 的值向下尋找到：`https://baking-revenge.fhh4ck3rs.taipei/users/65536`，就看到 flag 了：`FhCTF{IDOR_1s_t3rr4bl3_w1th_n0_l1m173d...}`
