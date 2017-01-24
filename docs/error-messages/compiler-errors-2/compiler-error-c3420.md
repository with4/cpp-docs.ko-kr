---
title: "컴파일러 오류 C3420 | Microsoft Docs"
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
  - "C3420"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3420"
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3420
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'finalizer': 종료자는 virtual일 수 없습니다.  
  
 종료자는 바깥쪽 형식에서 비가상으로만 호출할 수 있습니다. 따라서 가상 종료자를 선언하면 오류가 발생합니다.  
  
 자세한 내용은 [Visual C\+\+의 소멸자 및 종료자](../../misc/destructors-and-finalizers-in-visual-cpp.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3420을 생성합니다.  
  
```  
// C3420.cpp // compile with: /clr /c ref class R { virtual !R() {}   // C3420 };  
```