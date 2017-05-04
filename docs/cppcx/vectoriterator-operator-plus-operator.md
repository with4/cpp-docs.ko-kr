---
title: "VectorIterator::operator+ 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator+"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator+ 연산자"
ms.assetid: 5e907537-7d10-4766-a412-e7ea08b3456a
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator+ 연산자
지정된 VectorIterator에서 지정된 치환에 해당하는 요소를 참조하는 VectorIterator를 반환합니다.  
  
## 구문  
  
```  
  
VectorIterator operator+(  
   difference_type n) ;  
  
template <  
   typename T  
>  
inline VectorIterator<T> operator+(  
   ptrdiff_t n,  
   const VectorIterator<T>& i  
);  
  
```  
  
#### 매개 변수  
 `T`  
 두 번째 구문에서 VectorIterator의 형식 이름입니다.  
  
 `n`  
 정수 치환입니다.  
  
 `i`  
 두 번째 구문의 VectorIterator입니다.  
  
## 반환 값  
 첫 번째 구문에서 현재 VectorIterator에서 지정된 치환에 해당하는 요소를 참조하는 VectorIterator입니다.  
  
 두 번째 구문에서 매개 변수 `i` 시작 부분의 지정된 치환에 해당하는 요소를 참조하는 VectorIterator입니다.  
  
## 설명  
 첫 번째 구문 예제  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)