---
title: "BackInsertIterator::operator= 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator= 연산자"
ms.assetid: 509c9b4c-14fb-4318-bf65-b8926cc72f4f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator= 연산자
지정된 개체를 현재 순차 컬렉션의 끝에 추가합니다.  
  
## 구문  
  
```  
  
BackInsertIterator& operator=(  
   const T& t  
);  
```  
  
#### 매개 변수  
 `t`  
 현재 컬렉션에 추가할 개체입니다.  
  
## 반환 값  
 현재 BackInsertIterator에 대한 참조입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::BackInsertIterator 클래스](../cppcx/platform-collections-backinsertiterator-class.md)