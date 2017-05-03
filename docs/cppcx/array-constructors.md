---
title: "Array 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array::Array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Array::Array"
ms.assetid: befb8088-3915-4b5c-b7fd-90f79961412d
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Array 생성자
클래스 템플릿 매개 변수 *T*로 지정된 수정 가능한 1차원 형식 배열을 초기화합니다.  
  
## 구문  
  
```  
  
Array(unsigned int size);  
Array(T* data, unsigned int size);  
  
```  
  
#### 매개 변수  
 `T`  
 클래스 템플릿 매개 변수입니다.  
  
 `size`  
 배열의 요소 수입니다.  
  
 `data`  
 이 Array 개체를 초기화하는 데 사용되는 `T` 형식 데이터의 배열에 대한 포인터입니다.  
  
## 설명  
 Platform::Array 인스턴스를 만드는 방법에 대한 자세한 내용은 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)를 참조하세요.  
  
## 요구 사항  
 **헤더:** vccorlib.h  
  
 **네임스페이스:** Platform  
  
## 참고 항목  
 [Platform::Array 클래스](../cppcx/platform-array-class.md)