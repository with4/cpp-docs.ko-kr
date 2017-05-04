---
title: "VectorViewIterator::operator!= 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator!= 연산자"
ms.assetid: 00d55da7-9d85-495b-baaa-b5cdfa81aa7d
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator!= 연산자
현재 VectorViewIterator가 지정된 VectorViewIterator와 같지 않은지 여부를 나타냅니다.  
  
## 구문  
  
```  
bool operator!=(  
   const VectorViewIterator& other  
) const;  
```  
  
#### 매개 변수  
 `other`  
 다른 VectorViewIterator입니다.  
  
## 반환 값  
 현재 VectorViewIterator가 `other`와 같지 않으면 `true`이고, 같으면 `false`입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::VectorViewIterator 클래스](../cppcx/platform-collections-vectorviewiterator-class.md)