---
title: "VectorViewIterator::operator- 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator- 연산자"
ms.assetid: 03935872-8acc-4919-ae14-f375ca738aac
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator- 연산자
현재 반복기에서 지정된 요소 수를 빼서 새 반복기를 계산하거나 현재 반복기에서 지정된 반복기를 빼서 반복기 간 요소 수 차이를 계산합니다.  
  
## 구문  
  
```  
  
VectorViewIterator operator-(  
   difference_type n  
) const;  
  
difference_type operator-(  
   const VectorViewIterator& other  
) const;  
```  
  
#### 매개 변수  
 `n`  
 요소 수입니다.  
  
 `other`  
 다른 VectorViewIterator입니다.  
  
## 반환 값  
 첫 번째 연산자 구문은 현재 VectorViewIterator에서 `n`개 요소를 뺀 VectorViewIterator 개체를 반환합니다. 두 번째 구문은 현재 VectorViewIterator와 `other` VectorViewIterator의 요소 수 차이를 반환합니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::VectorViewIterator 클래스](../cppcx/platform-collections-vectorviewiterator-class.md)