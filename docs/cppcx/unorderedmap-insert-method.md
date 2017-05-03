---
title: "UnorderedMap::Insert 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::Insert"
ms.assetid: 89d55301-3cad-4877-825b-35096a1dd740
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::Insert 메서드
지정한 키\-값 쌍을 현재 UnorderedMap 개체에 추가합니다.  
  
## 구문  
  
```cpp  
  
virtual bool Insert(  
   K key,   
   V value  
);  
```  
  
#### 매개 변수  
 `key`  
 키\-값 쌍의 키 부분입니다.`key`의 형식은 형식 이름 *K*입니다.  
  
 `value`  
 키\-값 쌍의 값 부분입니다.`value` 형식은 형식 이름 *V*입니다.  
  
## 반환 값  
 현재 Map의 기존 요소 키가 `true`와 일치하고 해당 요소의 값 부분이 `key`로 설정된 경우 `value`입니다. 현재 Map의 기존 요소가 `false`와 일치하지 않고 `key` 및 `key` 매개 변수가 키\-값 쌍으로 생성된 후 현재 UnorderedMap에 추가된 경우 `value`입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections