---
title: 📝Macで署名してない開発中のCEPパネルが起動しない
date: 2023-02-15
tags:
  - program
  - script
---

ウィンドウ > エクステンション に名前は見えてるのにクリックしてもパネルが出てこない。

# やったこと
- デバッグモードをオンに
- Mac再起動
- Mac10.9以降に搭載された環境設定をキャッシュするプログラムを強制終了(cfprefsd)
- ZXP Installerをインストール ←これで解決

**Backlinks**
- [📝CEP作る]({{<ref "posts/202301162210-cep.md">}})  
- [⌨️Script]({{<ref "posts/202301071000-script.md">}})  