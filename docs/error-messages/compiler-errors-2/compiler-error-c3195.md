---
title: "컴파일러 오류 C3195 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3195"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3195"
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3195
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': 예약어이므로 값 형식 또는 ref 클래스의 멤버로 사용할 수 없습니다.CLR 또는 WinRT 연산자는 'operator' 키워드를 사용하여 정의해야 합니다.  
  
 컴파일러가 Managed Extensions for C\+\+ 구문을 사용하는 연산자 정의를 발견했습니다.  
  
 새 C\+\+ 구문을 사용하거나, **\/clr:oldSyntax** 컴파일러 옵션을 통해 Managed Extensions for C\+\+ 구문을 사용하도록 설정합니다.  
  
 다음 샘플에서는 C3195 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3195.cpp  
// compile with: /clr /LD  
#using <mscorlib.dll>  
value struct V {  
   static V op_Addition(V v, int i);   // C3195  
   static V operator +(V v, char c);   // OK for new C++ syntax   
};  
```