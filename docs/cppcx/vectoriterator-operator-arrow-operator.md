---
title: "VectorIterator::operator-&gt; 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator-> 연산자"
ms.assetid: d6caed5c-4899-45f8-95a2-687eafeeb8e1
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator-&gt; 연산자
현재 VectorIterator가 참조하는 요소의 주소를 검색합니다.  
  
## 구문  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
## 반환 값  
 현재 VectorIterator가 참조하는 요소의 값입니다.  
  
 반환 값의 형식은 이 연산자의 구현에 필요한 지정되지 않은 내부 형식입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::VectorIterator 클래스](../cppcx/platform-collections-vectoriterator-class.md)