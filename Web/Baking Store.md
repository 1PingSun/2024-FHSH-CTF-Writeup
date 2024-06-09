# Baking Store

Author: 孫逸平

Date: 2024-06-08

Link: https://ctfd.fhh4ck3rs.taipei/challenges#Baking%20Store-33

## 題目說明

烘焙時間！

> Author: CXPh03n1x

烤東西，烤東西！

但是好像會烤到不該烤的？

> **Hint:**
>
> 呵呵...這個要等 1 年是哪招...
> 可是，瀏覽器是怎麼知道「你」要等多久？

## Write-up

1. 將「旗」放進烤箱，發現要等待 31536000.0 秒，但沒有美國時間等那麼久。
2. 查看 Cookie 發現一個名為 `baking` 的 Cookie，其值看似一個 base64 編碼：`N2IyMjY5NjQyMjNhMjI2NjZjNjE2NzIyMmMyMjZlNjE2ZDY1MjIzYTIyZTY5Nzk3MjIyYzIyNzQ2OTZkNjUyMjNhMzMzMTM1MzMzNjMwMzAzMDMwMzAzMDJjMjI3Mzc0NjE3Mjc0NWY3NDY5NmQ2NTIyM2EzMTM3MzEzNzM4MzMzNjMyMzEzNzM5MzQzNzdk`
3. 透過 base64 解碼得到一個看似 Hex 值的東東，將其經過 Hex to ASCII Text String 得到：`{"id":"flag","name":"æ","time":31536000000,"start_time":1717836217947}`
4. 將當中的 time 值改為 `1`，並透過 ASCII Text String to Hex 加密，再經過 base64 加密得到：`N0IyMjY5NjQyMjNBMjI2NjZDNjE2NzIyMkMyMjZFNjE2RDY1MjIzQTIyRTY5Nzk3MjIyQzIyNzQ2OTZENjUyMjNBMzEyQzIyNzM3NDYxNzI3NDVGNzQ2OTZENjUyMjNBMzEzNzMxMzczODMzMzYzMjMxMzczOTM0Mzc3RA==`
5. 將 Cookie 中的 `baking` 值改為加密後的密文，就看到 flag 了：`FhCTF{Cl13nt_s1d3_auth0r1z3d_1s_d4ng3r!!!!}`
