---
title: "컴파일러 경고 (수준 1) C4096 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4096"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4096"
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4096
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'a': 인터페이스가 COM 인터페이스가 아니므로 IDL로 내보내지 않습니다.  
  
 COM 인터페이스로 계획했던 인터페이스 정의가 COM 인터페이스로 정의되지 않았으므로 IDL 파일로 내보내지지 않습니다.  
  
 인터페이스가 COM 인터페이스인지 여부를 나타내는 목록 특성에 대한 내용은 [interface attribute](../../windows/interface-attributes.md)을 참조하십시오.  
  
 다음 샘플에서는 C4096 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4096.cpp  
// compile with: /W1 /LD  
#include "windows.h"  
[module(name="xx")];  
  
// [object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct b : a  
{  
};   // C4096, remove coclass or uncomment object  
```