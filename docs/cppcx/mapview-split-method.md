---
title: "MapView::Split 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::Split"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::Split 메서드"
ms.assetid: b863e223-2282-4d1a-b995-77a690120542
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::Split 메서드
현재 MapView 개체를 두 개의 MapView 개체로 분할합니다. 이 메서드는 작동하지 않습니다.  
  
## 구문  
  
```  
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
 원래 MapView 개체의 첫 번째 부분입니다.  
  
 `secondPartition`  
 원래 MapView 개체의 두 번째 부분입니다.  
  
## 설명  
 이 메서드는 작동하지 않으며, 아무 작업도 수행하지 않습니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::MapView 클래스](../cppcx/platform-collections-mapview-class.md)