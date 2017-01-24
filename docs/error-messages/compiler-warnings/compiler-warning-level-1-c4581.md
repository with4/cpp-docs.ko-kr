---
title: "컴파일러 경고 (수준 1) C4581 | Microsoft Docs"
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
  - "C4581"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4581"
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4581
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용되지 않는 동작: 특성을 처리하기 위해 '"string1"'을\(를\) 'string2'\(으\)로 바꿨습니다.  
  
 이 오류는 Visual C\+\+ 2005에 대해 적용되었으며, Visual C\+\+ 특성의 매개 변수 확인이라는 컴파일러 규칙의 결과로 발생할 수 있습니다.  
  
 이전 버전에서는 특성 값이 따옴표로 묶여 있는지 여부와 상관없이 해당 값을 사용할 수 있었습니다.  새 버전의 경우 이 값이 열거형이면 이를 따옴표로 묶지 말아야 합니다.  
  
## 예제  
 다음 샘플에서는 C4581 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4581.cpp  
// compile with: /c /W1  
#include "unknwn.h"  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI : IUnknown {};  
  
[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581  
// try the following line instead  
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]  
class CSample : public IMyI {};  
```