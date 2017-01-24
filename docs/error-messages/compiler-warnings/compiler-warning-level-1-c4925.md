---
title: "컴파일러 경고(수준 1) C4925 | Microsoft Docs"
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
  - "C4925"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4925"
ms.assetid: a4b206c0-016a-4f28-873a-bb8bb41bad50
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4925
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method': 스크립트에서 dispinterface 메서드를 호출할 수 없습니다.  
  
 스크립트 언어에서 VT\_BYREF 'in' 매개 변수를 만들 수 없습니다. VT\_BYREF 'out' 매개 변수만 만들 수 있습니다.  
  
 이 경고를 해결하는 다른 방법은 매개 변수\(정의 및 구현\)를 포인터 형식으로 설정하지 않는 것입니다.  
  
 다음 샘플에서는 C4925를 생성합니다.  
  
```  
// C4925.cpp // compile with: /LD /W1 #define _ATL_ATTRIBUTES 1 #include <atlbase.h> #include <atlcom.h> [ module(name="Test")]; [ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ] __interface IDisp { [id(9)] void f([in] int*); }; [ coclass, uuid("00000000-0000-0000-0000-000000000002")  ] struct CDisp : IDisp {   // C4925 void f(int*) {} };  
```