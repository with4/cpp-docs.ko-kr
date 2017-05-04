---
title: "VectorView::GetAt 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::GetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::GetAt 메서드"
ms.assetid: 01c5feda-2a97-4429-ae15-4aced96ce332
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::GetAt 메서드
지정된 인덱스가 나타내는 현재 VectorView의 요소를 검색합니다.  
  
## 구문  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
#### 매개 변수  
 `index`  
 VectorView 개체의 특정 요소를 지정하는 0부터 시작하는 부호 없는 정수입니다.  
  
## 반환 값  
 `index` 매개 변수로 지정된 요소입니다. 요소 형식은 VectorView 템플릿 매개 변수 *T*로 지정됩니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [VectorView Class](http://msdn.microsoft.com/ko-kr/79697692-ae58-40e0-958f-cf1be6347994)