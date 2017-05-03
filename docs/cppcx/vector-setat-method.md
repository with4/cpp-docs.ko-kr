---
title: "Vector::SetAt 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::SetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::SetAt"
ms.assetid: ddfb454e-dbfd-4831-b040-674b085d8fb6
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::SetAt 메서드
현재 Vector에서 지정된 인덱스로 식별되는 요소에 지정된 값을 할당합니다.  
  
## 구문  
  
```  
  
virtual void SetAt(  
   unsigned int index,   
   T item  
);  
```  
  
#### 매개 변수  
 `index`  
 Vector 개체의 특정 요소를 지정하는 0부터 시작하는 부호 없는 정수입니다.  
  
 `item`  
 지정된 요소에 할당할 값입니다.`item` 형식은 *T* 형식 이름으로 정의됩니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md)