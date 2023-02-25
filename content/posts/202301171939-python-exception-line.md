---
title: ⌨️Python の例外処理で何行目がエラーを吐いたか出力させる
date: 2023-01-17
tags:
  - program
---

```python
import os, sys
try:
  hogehoge()
except Exception as e:
  exc_type, exc_obj, exc_tb = sys.exc_info()
  fname = os.path.split(exc_tb.tb_frame.f_code.co_filename)[1]
  print(e, fname, exc_tb.tb_lineno)
```