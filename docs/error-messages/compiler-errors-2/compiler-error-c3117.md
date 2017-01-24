---
title: "컴파일러 오류 C3117 | Microsoft Docs"
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
  - "C3117"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3117"
ms.assetid: dceee392-d4c7-4599-b75e-7aaac7c36fdd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3117
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'%$S' : 인터페이스에 기본 클래스를 하나만 사용할 수 있습니다.  
  
 여러 기본 클래스에서 상속한 인터페이스를 선언했습니다.  
  
 다음 샘플에서는 C3117 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3117.cpp  
#include <windows.h>  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I1  
{  
};  
  
[ object, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface I2  
{  
};  
  
[ object, uuid("00000000-0000-0000-0000-000000000003") ]  
__interface I3 : I1, I2  
{   // C3117  
};  
```