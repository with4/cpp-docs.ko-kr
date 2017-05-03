---
title: "Vector::IndexOf 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::IndexOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::IndexOf 메서드"
ms.assetid: 4a965992-3858-4e3f-992a-b94c0580b2f7
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::IndexOf 메서드
현재 Vector에서 지정한 항목을 검색하고 있는 경우 항목의 인덱스를 반환합니다.  
  
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
  
 항목이 Vector의 첫 번째 요소이거나 항목을 찾을 수 없으면 `index` 매개 변수가 0입니다. 반환 값이 `true`일 경우 항목을 찾았고 첫 번째 요소인 것이며, 그렇지 않으면 항목을 찾지 못한 것입니다.  
  
## 반환 값  
 지정된 항목을 찾았으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 설명  
 IndexOf는 std::find\_if를 사용하여 항목을 찾습니다. 그러므로 find\_if에 필요한 같음 비교를 사용하려면 사용자 지정 요소 형식이 \=\= 및 \!\= 연산자를 오버로드해야 합니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md)