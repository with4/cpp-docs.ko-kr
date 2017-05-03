---
title: "VectorViewIterator::operatorOperator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator[] 연산자"
ms.assetid: 41bf327d-2037-457c-83df-6338fc1abbc2
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operatorOperator
현재 VectorViewIterator에서 지정된 치환에 해당하는 요소에 대한 참조를 검색합니다.  
  
## 구문  
  
```  
reference operator[](difference_type n) const;  
```  
  
#### 매개 변수  
 `n`  
 정수 치환입니다.  
  
## 반환 값  
 현재 VectorViewIterator에서 `n` 요소에 의해 치환되는 요소입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::VectorViewIterator 클래스](../cppcx/platform-collections-vectorviewiterator-class.md)