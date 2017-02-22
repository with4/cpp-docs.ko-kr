---
title: "컴파일러 오류 C3461 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3461"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3461"
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3461
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 관리되는 형식만 전달할 수 있습니다.  
  
 형식 전달은 CLR 형식에서만 발생할 수 있습니다.  자세한 내용은 [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)를 참조하세요.  
  
 자세한 내용은 [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C3461.cpp // compile with: /clr /LD public ref class R {};  
```  
  
## 예제  
 다음 샘플에서는 C3461을 생성합니다.  
  
```  
// C3461b.cpp // compile with: /clr /c #using "C3461.dll" class N {}; [assembly:TypeForwardedTo(N::typeid)];   // C3461 [assembly:TypeForwardedTo(R::typeid)];   // OK  
```