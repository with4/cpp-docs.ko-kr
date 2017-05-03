---
title: "WriteOnlyArray::set 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::set 함수"
ms.assetid: 0359f922-f25e-47d1-b7df-87e7fd0f76e5
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::set 함수
지정한 인덱스의 지정된 값을 배열에 설정합니다.  
  
## 구문  
  
```cpp  
T& set(  
   unsigned int indexArg,  
   T valueArg);  
```  
  
#### 매개 변수  
 `indexArg`  
 설정할 요소의 인덱스입니다.  
  
 `valueArg`  
 `indexArg`에서 설정할 값입니다.  
  
## 반환 값  
 방금 설정한 요소에 대한 참조입니다.  
  
## 요구 사항  
 **헤더:** vccorlib.h  
  
 **네임스페이스:** Platform  
  
## 참고 항목  
 [Platform::WriteOnlyArray 클래스](../cppcx/platform-writeonlyarray-class.md)   
 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)