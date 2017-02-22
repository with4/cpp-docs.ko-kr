---
title: "Compiler Error C2396 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2396"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2396"
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compiler Error C2396
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'your\_type::operator'type'' : CLR 또는 WinRT 사용자 정의 변환 함수가 잘못되었습니다.다음에서 변환되거나 다음으로 변환해야 합니다. 'T^', 'T^%', 'T^&'\(T \= 'your\_type'\)  
  
 Windows 런타임 또는 관리되는 형식의 변환 함수에 해당 형식이 변환 함수를 포함하는 형식과 동일한 매개 변수가 하나 이상 없습니다.  
  
 다음 샘플에서는 C2396을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2396.cpp  
// compile with: /clr /c  
  
ref struct Y {  
   static operator int(char c);   // C2396  
  
   // OK  
   static operator int(Y^ hY);  
   // or  
   static operator Y^(char c);  
};  
```