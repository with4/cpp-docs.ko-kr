---
title: "BackInsertIterator::BackInsertIterator 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::BackInsertIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::BackInsertIterator 생성자"
ms.assetid: ae6f0213-a7bb-43b8-9a5e-7a8dad7c76f8
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::BackInsertIterator 생성자
`BackInsertIterator` 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```  
  
explicit BackInsertIterator(  
   Windows::Foundation::Collections::IVector<T>^ v  
);  
```  
  
#### 매개 변수  
 `v`  
 IVector\<T\> 개체입니다.  
  
## 설명  
 `BackInsertIterator`는 `v` 매개 변수로 지정된 개체의 마지막 요소 뒤에 요소를 삽입합니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::BackInsertIterator 클래스](../cppcx/platform-collections-backinsertiterator-class.md)