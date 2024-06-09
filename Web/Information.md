# Title

Author: 孫逸平

Date: 2024-06-08

Link: https://ctfd.fhh4ck3rs.taipei/challenges#Information-29

## 題目說明

資訊是種很玄的東西，他如影隨形～

> Author: CXPh03n1x

所以，我們更要好好保護！

> **Hint:**
>
> 非 SQL Injection 題型

> **Hint:**
>
> 請看看 Response Header 有什麼神奇的東西？
> 到底誰會在 ＯＯ 模式下就上線啊！！！
>
> 這樣不就會有很多曝光嗎！？

## Write-up

1. 觀察 Response Header 發現是使用 FastAPI 且為 Development Mode。
2. 上網搜尋找到 API 的路徑可能在 `/docs` 或 `redoc`。
3. 嘗試後發現可進入 `/redoc`。
4. 發現其中有一個名為 `Get Flag` 的 API，他是利用 GET 方式向 `https://information.fhh4ck3rs.taipei/flag_MDAwMDAwMDA6IDBhICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgLgo=` 發送請求。
5. 故利用瀏覽器打開此連結，就看到 flag 了：`FhCTF{Y0u_r3411y_n33d_t0_l0ck_y0ur_API_d0cum3n75}`
