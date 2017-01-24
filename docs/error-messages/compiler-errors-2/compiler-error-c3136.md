---
title: "컴파일러 오류 C3136 | Microsoft Docs"
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
  - "C3136"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3136"
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3136
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : COM 인터페이스는 다른 COM 인터페이스에서만 상속할 수 있는데, 'interface'은\(는\) COM 인터페이스가 아닙니다.  
  
 [interface attribute](../../windows/interface-attributes.md)을 적용한 인터페이스가 COM 인터페이스가 아닌 인터페이스에서 상속됩니다.  COM 인터페이스는 궁극적으로 `IUnknown`에서 상속됩니다.  인터페이스 특성 다음에 오는 인터페이스가 COM 인터페이스입니다.  
  
 다음 예제는 C3136을 발생시킵니다.  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```