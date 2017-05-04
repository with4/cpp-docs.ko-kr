---
title: "VectorViewIterator::operator+ 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator+"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator+ 연산자"
ms.assetid: 8206de2f-61b3-49cd-9715-d57695d880b3
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator+ 연산자
지정된 VectorViewIterator에서 지정된 치환에 해당하는 요소를 참조하는 VectorViewIterator를 반환합니다.  
  
## 구문  
  
```  
  
VectorViewIterator operator+(  
   difference_type n  
) const;  
  
template <  
   typename T  
>   
inline VectorViewIterator<T> operator+  
   (ptrdiff_t n,   
   const VectorViewIterator<T>& i  
);  
  
```  
  
#### 매개 변수  
 `T`  
 두 번째 구문에서 VectorViewIterator의 형식 이름입니다.  
  
 `n`  
 정수 치환입니다.  
  
 `i`  
 두 번째 구문의 VectorViewIterator입니다.  
  
## 반환 값  
 첫 번째 구문에서 현재 VectorViewIterator에서 지정된 치환에 해당하는 요소를 참조하는 VectorViewIterator입니다.  
  
 두 번째 구문에서 매개 변수 `i` 시작 부분의 지정된 치환에 해당하는 요소를 참조하는 VectorViewIterator입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::VectorViewIterator 클래스](../cppcx/platform-collections-vectorviewiterator-class.md)