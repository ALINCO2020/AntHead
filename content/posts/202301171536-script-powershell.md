---
title: 📝スクリプトから powershell を実行
date: 2023-01-17
tags:
  - program
  - script
---

- up: [⌨️Script]({{<ref "posts/202301071000-script.md">}})

直接 powershell.exe は実行できないから cmd.exe から起動する。  

```javascript
system.callSystem("cmd.exe /c powershell.exe -c \" your code \";");
```