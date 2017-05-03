---
title: "UnorderedMap::HasKey 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::HasKey"
ms.assetid: 7c397cdc-82f6-470a-8a3c-f5ba2cc58ed6
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::HasKey 메서드
현재 UnorderedMap에 지정한 키가 들어 있는지 여부를 확인합니다.  
  
## 구문  
  
```scr  
  
bool HasKey(  
   K key  
);  
```  
  
#### 매개 변수  
 `key`  
 UnorderedMap 요소를 찾는 데 사용되는 키입니다.`key`의 형식은 형식 이름 *K*입니다.  
  
## 반환 값  
 키가 있으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::UnorderedMap 클래스](../cppcx/platform-collections-unorderedmap-class.md)   
 [컬렉션](../cppcx/collections-c-cx.md)   
 [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)