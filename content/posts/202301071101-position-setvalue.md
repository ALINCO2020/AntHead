---
title: ⌨️位置にSetValueする関数
date: 2023-01-07
tags:
  - program
  - script
---

- up: [⌨️Script]({{<ref "posts/202301071000-script.md">}})

位置にSetValueするのがなかなか面倒くさいので関数を作った。けどあんまり使ってない。

```javascript
/**
* ポジションを設定する関数
* @param {*} layer レイヤー
* @param {*} XYarray 配列[x, y, z]
* @param {boolean} isSetValueAtTime setValueAtTimeを使うかどうか
* @param {*} time setValueAtTimeを使う場合の時間
*/
function setPosition(layer, XYZarray, isSetValueAtTime, time) {
  try {
    var x = XYZarray[0]
    var y = XYZarray[1]
    var z = XYZarray[2]
    var position = layer.property('ADBE Transform Group').property('ADBE Position')
    // setValueを使う場合
    if (!isSetValueAtTime) {
      // 次元分割されていない場合
      if (!position.dimensionsSeparated) {
        position.setValue([x, y, z])
      } else {// 次元分割されている場合
        layer.property("ADBE Transform Group").property("ADBE Position_0").setValue(x)
        layer.property("ADBE Transform Group").property("ADBE Position_1").setValue(y)
        if (layer.threeDLayer) {
          layer.property("ADBE Transform Group").property("ADBE Position_2").setValue(z)
        }
      }
    } else {// setValueAtTimeを使う場合
      // 次元分割されていない場合
      if (!position.dimensionsSeparated) {
        position.setValueAtTime(time, [x, y, z])
      } else {// 次元分割されている場合
        layer.property("ADBE Transform Group").property("ADBE Position_0").setValueAtTime(time, x)
        layer.property("ADBE Transform Group").property("ADBE Position_1").setValueAtTime(time, y)
        if (layer.threeDLayer) {
          layer.property("ADBE Transform Group").property("ADBE Position_2").setValueAtTime(time, z)
        }

      }
    }
  } catch (e) {
    alert(e.message + e.line)
  }
}
```