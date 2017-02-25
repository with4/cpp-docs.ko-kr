---
title: "컴파일러 오류 C3139 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3139"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3139"
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3139
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'struct' : 멤버 없이 UDT를 내보낼 수 없습니다.  
  
 빈 UDT\(사용자 정의 형식\)에 [export](../../windows/export.md) 특성을 적용하려고 했습니다.  예를 들면 다음과 같습니다.  
  
```  
// C3139.cpp  
#include "unknwn.h"  
[emitidl];  
[module(name=xx)];  
  
[export] struct MyStruct {   // C3139 empty type  
};  
int main(){}  
```