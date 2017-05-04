---
title: "UnorderedMap::GetView 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::GetView"
ms.assetid: 41a12802-3f42-461c-a6fc-a35fc34517f2
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::GetView 메서드
현재 UnorderedMap의 읽기 전용 뷰\([Windows::Foundation::Collections::IMapView::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) 인터페이스를 구현하는 [Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md)\)를 반환합니다.  
  
## 구문  
  
```scr  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
## 반환 값  
 `UnorderedMapView` 개체입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [컬렉션](../cppcx/collections-c-cx.md)   
 [Platform::Collections::UnorderedMap 클래스](../cppcx/platform-collections-unorderedmap-class.md)   
 [Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md)