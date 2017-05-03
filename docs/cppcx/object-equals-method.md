---
title: "Object::Equals 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::Equals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform, Object::Equals"
ms.assetid: 263ccd41-2a29-4716-a47e-4bf2883f3403
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::Equals 메서드
지정한 개체와 현재 개체가 같은지 여부를 확인합니다.  
  
## 구문  
  
```cpp  
  
bool Equals(  
    Object^ obj  
)  
```  
  
## 매개 변수  
 obj  
 비교할 개체입니다.  
  
## 반환 값  
 개체가 동일하면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::Object 클래스](../cppcx/platform-object-class.md)