# INDEX 與 RULES 的差集

Author: 孫逸平

Date: 2024-06-08

Link: https://ctfd.fhh4ck3rs.taipei/challenges#INDEX%20%E8%88%87%20RULES%20%E7%9A%84%E5%B7%AE%E9%9B%86-2

## 題目說明

みんなさん

> Author: CXPh03n1x

你們都熟讀首頁與規則了嗎？

真的要好好熟讀喔！

> 真的要「熟讀」喔！！！！！

> **Hint:**
>
> 差集用邏輯運算表示為？

> **Hint:**
>
> 天阿，別忘記先轉在運算啊！

> **Hint:**
>
> 歐天啊...
> 到底多少人不喜歡看原始碼啦！！！！

## Write-up

1. 查看「首頁」的原始碼，看到一個 `<script>` 標籤中有一個 XOR 的變數：`RmhDVEZ7SDNsMW8gPC0tIHBhcnQgMS8y`
2. 其看似為 base64 編碼，因此進行 base64 解碼得到：`FhCTF{H3l1o <-- part 1/2`
3. 再查看「規則」的原始碼，找到一個註解包含看似 Hex 的值：`192b741219293d0209041200000000000000000000030000`
4. 將此 Hex 值與上方 base64 解碼後的值進行 xor 運算得到：`_C7F_Ru1e5} <-- part 2/2`
5. 由此可知上方第 2 步與第 4 步為 flag 的兩部分，組合後就得到 flag：`FhCTF{H3l1o_C7F_Ru1e5}`
