---
title: "Map::Lookup 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Lookup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Lookup 메서드"
ms.assetid: c56773ae-2df0-4d21-a6ab-9603529547b0
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Lookup 메서드
K 형식의 지정된 키\(해당 키가 있는 경우\)와 연결된 V 형식의 값을 검색합니다.  
  
## 구문  
  
```  
V Lookup(  
   K key  
);  
```  
  
#### 매개 변수  
 `key`  
 지도에서 요소를 찾는 데 사용되는 키입니다.`key`의 형식은 형식 이름 *K*입니다.  
  
## 반환 값  
 `key`와 쌍을 이루는 값입니다. 반환 값의 형식은 형식 이름 *V*입니다.  
  
## 설명  
 해당 키가 없으면 [Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md)이 throw됩니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md)   
 [컬렉션\(C\+\+\/CX\)](../cppcx/collections-c-cx.md)