---
title: "Map::HasKey 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::HasKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::HasKey 메서드"
ms.assetid: ba7864af-056a-4b7b-843d-08c45b7f7394
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::HasKey 메서드
현재 Map에 지정한 키가 들어 있는지 여부를 확인합니다.  
  
## 구문  
  
```  
  
bool HasKey(  
   K key  
);  
```  
  
#### 매개 변수  
 `key`  
 Map 요소를 찾는 데 사용되는 키입니다.`key`의 형식은 형식 이름 *K*입니다.  
  
## 반환 값  
 키가 있으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md)