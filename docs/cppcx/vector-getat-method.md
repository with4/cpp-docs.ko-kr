---
title: "Vector::GetAt 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::GetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::GetAt 메서드"
ms.assetid: 3766b399-cef2-4006-9a87-50f717390cac
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::GetAt 메서드
지정된 인덱스로 식별되는 현재 Vector의 요소를 검색합니다.  
  
## 구문  
  
```  
  
virtual T GetAt(  
   unsigned int index  
);  
```  
  
#### 매개 변수  
 `index`  
 Vector 개체의 특정 요소를 지정하는 0부터 시작하는 부호 없는 정수입니다.  
  
## 반환 값  
 `index` 매개 변수로 지정된 요소입니다. 요소 형식은 *T* 형식 이름으로 정의됩니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md)