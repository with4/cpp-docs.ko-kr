---
title: "WriteOnlyArray::begin 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::begin 메서드"
ms.assetid: 25025fa0-8f55-4abf-93ad-71db45ddfae3
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::begin 메서드
배열의 첫 번째 요소에 대한 포인터를 반환합니다.  
  
## 구문  
  
```cpp  
T* begin() const;  
```  
  
## 반환 값  
 배열의 첫 번째 요소에 대한 포인터입니다.  
  
## 설명  
 이 반복기를 `std::sort`와 같은 STL 알고리즘과 함께 사용하여 배열 요소에 대해 작업을 수행할 수 있습니다.  
  
## 요구 사항  
 **헤더:** vccorlib.h  
  
 **네임스페이스:** Platform  
  
## 참고 항목  
 [Platform::WriteOnlyArray 클래스](../cppcx/platform-writeonlyarray-class.md)   
 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)