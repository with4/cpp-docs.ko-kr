---
title: "VectorView::IndexOf 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::IndexOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::IndexOf 메서드"
ms.assetid: 848117ec-ad4a-4a0b-9c1e-9076e5188869
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::IndexOf 메서드
현재 VectorView에서 지정한 항목을 검색하고 있는 경우 항목의 인덱스를 반환합니다.  
  
## 구문  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
#### 매개 변수  
 `value`  
 찾을 항목입니다.  
  
 `index`  
 매개 변수 `value`가 있으면 0부터 시작하는 항목의 인덱스이고, 그렇지 않으면 0입니다.  
  
 항목이 VectorView의 첫 번째 요소이거나 항목을 찾을 수 없으면 `index` 매개 변수가 0입니다. 반환 값이 `true`일 경우 항목을 찾았고 첫 번째 요소인 것이며, 그렇지 않으면 항목을 찾지 못한 것입니다.  
  
## 반환 값  
 지정된 항목을 찾았으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [VectorView Class](http://msdn.microsoft.com/ko-kr/79697692-ae58-40e0-958f-cf1be6347994)