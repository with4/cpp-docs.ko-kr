---
title: "MapView::First 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::First 메서드"
ms.assetid: 9d7c7328-4f55-4ea6-a375-9d4e73707b56
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::First 메서드
맵 뷰의 첫 번째 요소를 지정하는 반복기를 반환합니다.  
  
## 구문  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^   
First();  
```  
  
## 반환 값  
 맵 뷰의 첫 번째 요소를 지정하는 반복기입니다.  
  
## 설명  
 First\(\)에서 반환된 반복기를 보유하는 편리한 방법은 [auto](../Topic/auto%20\(C++\).md) 형식 추론 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. 예를 들어, `auto x = myMapView->First();`을 입력합니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::MapView 클래스](../cppcx/platform-collections-mapview-class.md)