---
title: "컴파일러 오류 C3464 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3464"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3464"
ms.assetid: 0ede05dc-4486-4921-8e8c-78ab5a2e09c5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3464
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' 중첩 형식은 전달할 수 없습니다.  
  
 중첩 형식에는 형식 전달이 적용되지 않습니다.  
  
 자세한 내용은 [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C3464.cpp // compile with: /LD /clr public ref class R { public: ref class N {}; };  
```  
  
## 예제  
 다음 샘플에서는 C3464를 생성합니다.  
  
```  
// C3464_b.cpp // compile with: /clr /c #using "C3464.dll" [assembly:TypeForwardedTo(R::N::typeid)];   // C3464 [assembly:TypeForwardedTo(R::typeid)];   // OK  
```