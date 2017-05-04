---
title: "VectorViewIterator::operator-= 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator-="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator-= 연산자"
ms.assetid: fc4d5f19-a001-44fd-aabe-972d8b54ca2f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator-= 연산자
지정된 치환으로 현재 VectorIterator를 줄입니다.  
  
## 구문  
  
```  
VectorViewIterator& operator-=(  
   difference_type n  
);  
```  
  
#### 매개 변수  
 `n`  
 정수 치환입니다.  
  
## 반환 값  
 업데이트된 VectorIterator입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::VectorViewIterator 클래스](../cppcx/platform-collections-vectorviewiterator-class.md)