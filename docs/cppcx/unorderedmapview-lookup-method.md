---
title: "UnorderedMapView::Lookup 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::Lookup"
ms.assetid: 22f61824-ba8c-4b8c-9077-7577c41a6742
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::Lookup 메서드
K 형식의 지정된 키와 연결된 V 형식의 값을 검색합니다.  
  
## 구문  
  
```cpp  
V Lookup(  
   K key  
);  
```  
  
#### 매개 변수  
 `key`  
 UnorderedMapView에서 요소를 찾는 데 사용되는 키입니다.`key`의 형식은 형식 이름 *K*입니다.  
  
## 반환 값  
 `key`와 쌍을 이루는 값입니다. 반환 값의 형식은 형식 이름 *V*입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md)