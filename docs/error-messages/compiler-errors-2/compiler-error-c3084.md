---
title: "컴파일러 오류 C3084 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3084"
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C3084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 종료자\/소멸자는 'keyword'가 될 수 없습니다.  
  
 종료자 또는 소멸자를 잘못 선언했습니다.  
  
 예를 들어 소멸자를 sealed로 표시하면 안 됩니다.  파생 형식이 소멸자에 액세스할 수 없습니다.  자세한 내용은 [명시적 재정의](../../windows/explicit-overrides-cpp-component-extensions.md) 및 [Visual C\+\+의 소멸자 및 종료자](../../misc/destructors-and-finalizers-in-visual-cpp.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3084를 생성합니다.  
  
```  
// C3084.cpp // compile with: /clr /c ref struct R { protected: !R() sealed;   // C3084 !R() abstract;   // C3084 !R(); };  
```