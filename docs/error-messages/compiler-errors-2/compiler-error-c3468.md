---
title: "컴파일러 오류 C3468 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3468"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3468"
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3468
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 어셈블리에만 형식을 전달할 수 있습니다.  
  
 '`file`'은 어셈블리가 아닙니다.  
  
 어셈블리의 형식만 전달할 수 있습니다.  
  
 자세한 내용은 [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 모듈을 만듭니다.  
  
```  
// C3468.cpp // compile with: /LN /clr public ref class R {};  
```  
  
## 예제  
 다음 샘플에서는 C3468을 생성합니다.  
  
```  
// C3468_b.cpp // compile with: /clr /c #using "C3468.netmodule" [ assembly:TypeForwardedTo(R::typeid) ];   // C3468  
```