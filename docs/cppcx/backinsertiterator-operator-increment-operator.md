---
title: "BackInsertIterator::operator++ 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator++ 연산자"
ms.assetid: 08324574-db2b-4d95-825e-a93a56f327da
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator++ 연산자
현재 BackInsertIterator에 대한 참조를 반환합니다. 반복기는 수정되지 않습니다.  
  
## 구문  
  
```  
  
BackInsertIterator& operator++();  
  
BackInsertIterator operator++(  
   int  
);  
```  
  
## 반환 값  
 현재 BackInsertIterator에 대한 참조입니다.  
  
## 설명  
 의도적으로, 첫 번째 구문 예는 현재 BackInsertIterator를 사전에 증가시키고 두 번째 구문은 현재 BackInsertIterator를 사후에 증가시킵니다. 두 번째 구문의 `int` 형식은 실제 정수 연산자가 아니라 후위 증가 연산을 나타냅니다.  
  
 그러나 이 연산자는 BackInsertIterator를 실제로 수정하지 않습니다. 대신에 수정되지 않은 현재 반복기에 대한 참조를 반환합니다. 이는 [연산자\*](../cppcx/backinsertiterator-operator-dereference-operator.md)와 동일한 동작입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::BackInsertIterator 클래스](../cppcx/platform-collections-backinsertiterator-class.md)