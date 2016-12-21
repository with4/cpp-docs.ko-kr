---
title: "컴파일러 오류 C3085 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3085"
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constructor': 생성자는 'keyword'일 수 없습니다.  
  
 생성자가 잘못 선언되었습니다. 자세한 내용은 [Override 지정자](../../windows/override-specifiers-cpp-component-extensions.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3085를 생성합니다.  
  
```  
// C3085.cpp // compile with: /c /clr ref struct S { S() abstract;   // C3085 S(S%) abstract;   // C3085 }; ref struct T { T() sealed {}   // C3085 T(T%) sealed {}   // C3085 };  
```