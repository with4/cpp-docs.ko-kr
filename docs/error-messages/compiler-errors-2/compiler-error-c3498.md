---
title: "Compiler Error C3498 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3498"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3498"
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3498
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 관리되는 또는 WinRT 형식인 변수를 캡처할 수 없습니다.  
  
 람다에 관리되는 형식 또는 Windows 런타임 형식이 있는 변수를 캡처할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   관리되는 또는 Windows 런타임 변수를 람다 식의 매개 변수 목록에 전달합니다.  
  
## 예제  
 다음 예제에서는 관리되는 형식이 있는 변수가 람다 식의 캡처 목록에 나타나므로 C3498을 생성합니다.  
  
```  
// C3498a.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [&s](String ^ r)   
      { return String::Concat(s, r); } (", World!"); // C3498  
}  
```  
  
## 예제  
 다음 예제에서는 관리되는 변수`s`를 람다 식의 매개 변수 목록에 전달하여 C3498을 해결합니다.  
  
```  
// C3498b.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [](String ^ s, String ^ r)   
      { return String::Concat(s, r); } (s, ", World!");  
}  
```  
  
## 참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)