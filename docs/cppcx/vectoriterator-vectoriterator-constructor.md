---
title: "VectorIterator::VectorIterator 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::VectorIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::VectorIterator 생성자"
ms.assetid: 93286731-9499-4bfb-a24b-b302479c38cc
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::VectorIterator 생성자
VectorIterator 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```  
  
VectorIterator();  
  
explicit VectorIterator(  
   Windows::Foundation::Collections::IVector<T>^ v  
);  
```  
  
#### 매개 변수  
 `v`  
 IVector\<T\> 개체입니다.  
  
## 설명  
 첫 번째 구문 예제에서는 기본 생성자를 호출합니다. 두 번째 구문 예제는 IVector\<T\> 개체에서 VectorIterator를 만드는 데 사용되는 명시적 생성자입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::VectorIterator 클래스](../cppcx/platform-collections-vectoriterator-class.md)