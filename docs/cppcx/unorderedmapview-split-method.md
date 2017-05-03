---
title: "UnorderedMapView::Split 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::Split"
ms.assetid: b759d254-40c9-40f1-9838-106ffb2c5626
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::Split 메서드
현재 UnorderedMapView 개체를 두 개의 UnorderedMapView 개체로 나눕니다. 이 메서드는 작동하지 않습니다.  
  
## 구문  
  
```cpp  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * secondPartition  
);  
```  
  
#### 매개 변수  
 `firstPartition`  
 원래 UnorderedMapView 개체의 첫 번째 부분입니다.  
  
 `secondPartition`  
 원래 UnorderedMapView 개체의 두 번째 부분입니다.  
  
## 설명  
 이 메서드는 작동하지 않으며, 아무 작업도 수행하지 않습니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md)