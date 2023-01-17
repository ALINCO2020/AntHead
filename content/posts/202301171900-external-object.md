---
title: 📝ExternalObject is 何
date: 2023-01-17
tags:
  - program
  - script
---

- up: [⌨️Script]({{<ref "posts/202301071000-script.md">}})

[.dll]({{<ref "posts/202301171909-dll.md">}}) を実行するとき使うやつ。以下の関数を実装する必要あり。  
- ESInitialize()  
- ESGetVersion()  
- ESFreeMem()  
- ESTerminate()  

参考 : [AfterEffects CS6でスクリプトから自作のDLLを参照する方法があるかどうか](https://teratail.com/questions/101556?link=qa_related_pc)  

これも ExternalObject 使ってる。.aex も中身は .dll みたいなものだったりする？  
[📝AEデフォルトのカラーピッカーを使う方法]({{<ref "posts/202301171848-default-color-picker.md">}})  