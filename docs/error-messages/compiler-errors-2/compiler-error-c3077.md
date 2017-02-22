---
title: "컴파일러 오류 C3077 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3077"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3077"
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3077
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'finalizer': 종료자는 참조 형식의 멤버만 될 수 있습니다.  
  
 종료자를 네이티브 또는 값 형식을 선언할 수 없습니다.  
  
 자세한 내용은 [Visual C\+\+의 소멸자 및 종료자](../../misc/destructors-and-finalizers-in-visual-cpp.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3077을 생성합니다.  
  
```  
// C3077.cpp // compile with: /clr /c value struct vs { !vs(){}   // C3077 }; ref struct rs { protected: !rs(){}   // OK };  
```