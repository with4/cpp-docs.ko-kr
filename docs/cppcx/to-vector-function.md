---
title: "to_vector 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::to_vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_vector 함수"
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# to_vector 함수
지정된 IVector 또는 IVectorView 매개 변수의 기본 컬렉션과 값이 같은 `std::vector`를 반환합니다.  
  
## 구문  
  
```  
template <  
   typename T  
>  
inline ::std::vector<T> to_vector(  
   IVector<T>^ v  
);  
template <  
   typename T  
>  
inline ::std::vector<T> to_vector(  
   IVectorView<T>^ v  
);  
```  
  
#### 매개 변수  
 `T`  
 템플릿 형식 매개 변수입니다.  
  
 `v`  
 기본 Vector 또는 VectorView 개체에 대한 액세스를 제공하는 IVector 또는 IVectorView 인터페이스입니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Windows::Foundation::Collections  
  
## 참고 항목  
 [Windows::Foundation::Collections 네임스페이스](../cppcx/windows-foundation-collections-namespace-c-cx.md)