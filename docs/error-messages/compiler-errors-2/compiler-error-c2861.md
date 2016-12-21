---
title: "컴파일러 오류 C2861 | Microsoft Docs"
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
  - "C2861"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2861"
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2861
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function name' : 인터페이스 멤버 함수를 정의할 수 없습니다.  
  
 컴파일러가 인터페이스 키워드를 발견하거나 구조체를 인터페이스로 추론했으나 멤버 함수 정의를 발견했습니다.  인터페이스에는 멤버 함수에 대한 정의가 포함될 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C2861 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2861.cpp  
// compile with: /c  
#include <objbase.h>   // required for IUnknown definition  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IMyInterface : IUnknown {  
   HRESULT mf(int a);  
};  
  
HRESULT IMyInterface::mf(int a) {}   // C2861  
  
```