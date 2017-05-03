---
title: "Map::MapChanged 이벤트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::MapChanged"
ms.assetid: d14b5b93-36ff-47a5-b588-dd1dc6ea4364
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::MapChanged 이벤트
맵에서 항목이 삽입되거나 제거될 때 발생합니다.  
  
## 구문  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
## 속성 값\/반환 값  
 이벤트를 발생시킨 개체에 대한 정보와 발생한 변경 내용의 종류가 들어 있는 [MapChangedEventHandler\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br206644.aspx)입니다.[IMapChangedEventArgs\<K\>](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) 및 [CollectionChange 열거형](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 C\# 또는 Visual Basic 프로젝트 IMap\<K,V\>을 IDictionary\<K,V\>로 사용하는 Windows 스토어 앱입니다.  
  
## 요구 사항  
 Windows 8.0 이상  
  
## 참고 항목  
 [컬렉션](../cppcx/collections-c-cx.md)