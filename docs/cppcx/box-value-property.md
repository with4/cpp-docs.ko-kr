---
title: "Box::Value 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::Value"
dev_langs: 
  - "C++"
ms.assetid: f456b105-6c14-4737-8c27-ad47d1eabd32
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::Value 속성
`Box` 개체에 캡슐화된 값을 반환합니다.  
  
## 구문  
  
```cpp  
virtual property T Value{  
   T get();  
}  
```  
  
## 반환 값  
 boxing되기 전 형식의 boxed 값을 반환합니다.  
  
## 요구 사항  
 **헤더:** vccorlib.h  
  
 **네임스페이스:** Platform  
  
## 참고 항목  
 [Platform::Box 클래스](../cppcx/platform-box-class.md)   
 [boxing](../cppcx/boxing-c-cx.md)