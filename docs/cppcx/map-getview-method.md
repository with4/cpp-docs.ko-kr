---
title: "Map::GetView 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::GetView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::GetView 메서드"
ms.assetid: d432bb98-d354-4caa-8c2b-794406ac0b0b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::GetView 메서드
현재 Map의 읽기 전용 뷰\([Windows::Foundation::Collections::IMapView\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) 인터페이스를 구현하는 [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)\)를 반환합니다.  
  
## 구문  
  
```  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
## 반환 값  
 `MapView` 개체입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md)   
 [Platform::Collections::UnorderedMapClass](../cppcx/platform-collections-unorderedmap-class.md)   
 [컬렉션\(C\+\+\/CX\)](../cppcx/collections-c-cx.md)