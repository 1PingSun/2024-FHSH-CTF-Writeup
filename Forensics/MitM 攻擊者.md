# MitM 攻擊者

Author: 孫逸平

Date: 2024-06-06

Link: https://ctfd.fhh4ck3rs.taipei/challenges#MitM%20%E6%94%BB%E6%93%8A%E8%80%85-10

## 題目說明

作為中間人的辛苦你懂嗎！！！
Author: Adams

就說了不要用不安全的協定，不要老是用不加密的協定......

就是

不聽！！！

反正，中間人就是肝苦啦！！

本題 Flag 有額外格式；`fhsfctf{\S}`

[ftp.pcap](./src/ftp.pcap)

## Write-up

1. 利用 Wireshark 打開檔案，在第 28 筆就可以看到 flag 了：`fhsfctf{w1ll_a1w4y5_pr3v4il}`
