---
title: "WriteOnlyArray::FastPass 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::FastPass"
dev_langs: 
  - "C++"
ms.assetid: f7a54ae0-afa0-4728-8736-c63933f789aa
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::FastPass 속성
내부 FastPass 최적화를 수행할 수 있는지 여부를 나타냅니다. 사용자 코드에서는 사용되지 않습니다.  
  
## 구문  
  
```cpp  
property bool FastPass{  
   bool get() const;  
}  
```  
  
## 반환 값  
 배열이 FastPass인지 여부를 나타내는 부울 값입니다.  
  
## 요구 사항  
 **헤더:** vccorlib.h  
  
 **네임스페이스:** Platform  
  
## 참고 항목  
 [Platform::WriteOnlyArray 클래스](../cppcx/platform-writeonlyarray-class.md)