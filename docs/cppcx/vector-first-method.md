---
title: "Vector::First 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::First 메서드"
ms.assetid: ca6b7b55-dd49-4346-bfa4-d8010b228d44
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::First 메서드
Vector의 첫 번째 요소를 가리키는 반복기를 반환합니다.  
  
## 구문  
  
```  
  
virtual Windows::Foundation::Collections::IIterator <T>^   
   First();  
```  
  
## 반환 값  
 Vector의 첫 번째 요소를 가리키는 반복기입니다.  
  
## 설명  
 First\(\)에서 반환된 반복기를 보유하는 편리한 방법은 [auto](../Topic/auto%20\(C++\).md) 형식 추론 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. 예를 들어, `auto x = myVector->First();`을 입력합니다. 이 반복기는 컬렉션의 길이를 알고 있습니다.  
  
 STL 함수에 전달되는 반복기 쌍이 필요한 경우 free 함수 [Windows::Foundation::Collections::begin](../cppcx/begin-function.md) 및 [Windows::Foundation::Collections::end](../cppcx/end-function.md)를 사용합니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md)   
 [컬렉션](../cppcx/collections-c-cx.md)