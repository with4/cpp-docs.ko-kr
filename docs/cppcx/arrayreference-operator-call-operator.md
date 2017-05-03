---
title: "ArrayReference::operator() 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::operatorArray^"
dev_langs: 
  - "C++"
ms.assetid: 48726344-82bb-4c1d-b246-ed74b895f99b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::operator() 연산자
현재 [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) 개체를 다시 [Platform::Array](../cppcx/platform-array-class.md) 클래스로 변환합니다.  
  
## 구문  
  
```cpp  
  
Array<__TArg>^ operator ();  
  
```  
  
## 반환 값  
 `Array<__TArg>^` 형식의 개체 핸들입니다.  
  
## 설명  
 [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md)와 [Platform::Array](../cppcx/platform-array-class.md)는 ref 클래스가 아닌 표준 C\+\+ 클래스 템플릿입니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::ArrayReference 클래스](../cppcx/platform-arrayreference-class.md)