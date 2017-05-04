---
title: "Array::get 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array::get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Array::get 메서드"
ms.assetid: 3bbcd829-35e7-4912-99ba-6ab9de407287
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Array::get 메서드
지정된 인덱스 위치에서 배열 요소에 대한 참조를 검색합니다.  
  
## 구문  
  
```  
  
T& get(  
unsigned int index  
)  const;  
```  
  
#### 매개 변수  
 `index`  
 배열에서 요소를 식별하는 0부터 시작하는 인덱스를 확인합니다. 최소 인덱스는 0이고 최대 인덱스는 [배열 생성자](../cppcx/array-constructors.md)의 `size` 매개 변수로 지정된 값입니다.  
  
## 반환 값  
 `index` 매개 변수로 지정된 배열 요소입니다.  
  
## 요구 사항  
 **헤더:** vccorlib.h  
  
 **네임스페이스:** Platform  
  
## 참고 항목  
 [Platform::Array 클래스](../cppcx/platform-array-class.md)