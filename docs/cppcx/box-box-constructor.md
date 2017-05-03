---
title: "Box::Box 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::Box"
dev_langs: 
  - "C++"
ms.assetid: 3c4777f0-801c-4b24-9426-6d658dfaecf8
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::Box 생성자
지정된 형식의 값을 캡슐화할 수 있는 `Box`를 만듭니다.  
  
## 구문  
  
```cpp  
Box(T valueArg);  
```  
  
#### 매개 변수  
 `valueArg`  
 boxing할 값의 형식입니다\(예: `int`, `bool`, `float64`, `DateTime`\).  
  
## 요구 사항  
 **헤더:** vccorlib.h  
  
 **네임스페이스:** Platform  
  
## 참고 항목  
 [Platform::Box 클래스](../cppcx/platform-box-class.md)   
 [boxing](../cppcx/boxing-c-cx.md)