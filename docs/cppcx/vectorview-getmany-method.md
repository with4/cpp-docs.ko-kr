---
title: "VectorView::GetMany 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::GetMany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::GetMany 메서드"
ms.assetid: 67d9348f-66fe-417e-9e25-5de0a3cd306c
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::GetMany 메서드
현재 VectorView에서 지정된 인덱스부터 시작하여 일련의 항목을 검색합니다.  
  
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
 이 작업이 완료되면 `startIndex`로 지정된 요소에서 시작해 VectorView의 마지막 요소에서 끝나는 항목의 배열입니다.  
  
## 반환 값  
 검색된 항목의 수입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [VectorView Class](http://msdn.microsoft.com/ko-kr/79697692-ae58-40e0-958f-cf1be6347994)