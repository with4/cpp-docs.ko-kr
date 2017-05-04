---
title: "VectorIterator::operator&gt;= 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator>= 연산자"
ms.assetid: 8154015e-8da7-4381-8128-d3669eb88e16
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator&gt;= 연산자
현재 VectorIterator가 지정된 VectorIterator보다 크거나 같은지 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
  
bool operator>=(  
   const VectorIterator& other  
) const   
```  
  
#### 매개 변수  
 `other`  
 다른 VectorIterator입니다.  
  
## 반환 값  
 현재 VectorIterator가 `true`보다 크거나 같으면 `other`이고, 그렇지 않으면 `false`입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::VectorIterator 클래스](../cppcx/platform-collections-vectoriterator-class.md)