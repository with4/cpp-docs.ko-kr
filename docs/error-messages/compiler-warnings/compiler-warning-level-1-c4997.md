---
title: "컴파일러 경고(수준 1) C4997 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4997"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4997"
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고(수준 1) C4997
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': coclass가 COM 인터페이스 또는 의사\(pseudo\) 인터페이스를 구현하지 않습니다.  
  
 [coclass](../../windows/coclass.md) 특성으로 표시된 클래스가 인터페이스를 구현하지 않았습니다.  
  
 다음 샘플에서는 C4997을 생성합니다.  
  
```  
// C4997.cpp // compile with: /WX // to resolve this C4997, uncomment all code #include <objbase.h> [ object ] __interface I { HRESULT func(); }; [ coclass ] struct C /*: I*/ { /* HRESULT func() { return S_OK; } */ };   // C4997  
```