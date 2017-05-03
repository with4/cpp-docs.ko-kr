---
title: "VectorViewIterator::operator&lt; 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator< 연산자"
ms.assetid: 411c9af9-78b1-4b1b-839b-3bec76020184
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator&lt; 연산자
현재 VectorIterator가 지정된 VectorIterator보다 작은지 여부를 나타냅니다.  
  
## 구문  
  
```  
bool operator<(  
   const VectorViewIterator& other  
) const;  
```  
  
#### 매개 변수  
 `other`  
 다른 VectorIterator입니다.  
  
## 반환 값  
 현재 VectorIterator가 `true`보다 작으면 `other`이고, 크거나 같으면 `false`입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::VectorViewIterator 클래스](../cppcx/platform-collections-vectorviewiterator-class.md)