---
title: "Vector::GetMany 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::GetMany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::GetMany 메서드"
ms.assetid: e2d5ccf4-101a-47e5-a0d8-56f65a7ff28d
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::GetMany 메서드
현재 Vector에서 지정된 인덱스부터 시작해 일련의 항목을 검색해서 호출자가 할당한 배열에 복사합니다.  
  
## 구문  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
#### 매개 변수  
 `startIndex`  
 검색할 항목 시작 부분의 0부터 시작하는 인덱스입니다.  
  
 `dest`  
 호출자가 할당한, `startIndex`로 지정된 요소에서 시작해 Vector의 마지막 요소에서 끝나는 항목의 배열입니다.  
  
## 반환 값  
 검색된 항목의 수입니다.  
  
## 설명  
 이 함수는 클라이언트 코드에서 직접 사용하지 않습니다. 이는 [to\_vector 함수](../cppcx/to-vector-function.md)에서 내부적으로 사용되어 Platform::Vector 인스턴스를 std::vector 인스턴스로 효율적으로 변환할 수 있습니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md)