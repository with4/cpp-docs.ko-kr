---
title: "VectorView::First 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::First 메서드"
ms.assetid: 543a5c5b-8ce3-4be3-9fad-726928de7855
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::First 메서드
VectorView의 첫 번째 요소를 지정하는 반복기를 반환합니다.  
  
## 구문  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
## 반환 값  
 VectorView의 첫 번째 요소를 지정하는 반복기입니다.  
  
## 설명  
 First\(\)에서 반환된 반복기를 보유하는 편리한 방법은 [auto](../Topic/auto%20\(C++\).md) 형식 추론 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. 예를 들어, `auto x = myVectorView->First();`을 입력합니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [VectorView Class](http://msdn.microsoft.com/ko-kr/79697692-ae58-40e0-958f-cf1be6347994)