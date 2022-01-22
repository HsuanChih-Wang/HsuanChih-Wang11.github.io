---
layout: post
title: Python ElementTree - TypeError cannot serialize xx (type int)
categories: publication
description: Python ElementTree 遇到 TypeError cannot serialize 錯誤解決方法
keywords: python
mathjax: true
---
最近使用Python ElementTree套件，建立一個新的xml後想要dump出來看看。

遇到錯誤:  TypeError cannot serialize xx (type int)

範例code: 
```python
import xml.etree.ElementTree as ET

# 建立新的 XML 結構
root = ET.Element('RiskyDrivingBehaviors')
#新增 vehicle 節點
vehicleNode = ET.SubElement(root, 'vehicle')
vehID = 1
vehicleNode.set("ID", vehID)

ET.dump(root)
```
錯誤訊息: 
```=python
TypeError: cannot serialize 1 (type int)
```

後來發現是因為xml節點裡面的參數值只能是string，給int會有錯誤
把int轉型為string就解決了

```python
import xml.etree.ElementTree as ET

# 建立新的 XML 結構
root = ET.Element('RiskyDrivingBehaviors')
#新增 vehicle 節點
vehicleNode = ET.SubElement(root, 'vehicle')
vehID = 1
vehicleNode.set("ID", str(vehID)) # int轉型為string

ET.dump(root)
```

正確顯示:
```xml
<RiskyDrivingBehaviors><vehicle ID="1" /></RiskyDrivingBehaviors>
```