---
title: "Compiler Error C2395 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2395"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2395"
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compiler Error C2395
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'your\_type::operator'op'' : CLR 또는 WinRT 연산자가 잘못되었습니다.하나 이상의 매개 변수가 'T', 'T%', 'T&', 'T^', 'T^%', 'T^&' 형식이어야 합니다. 여기서 T \= 'your\_type'입니다.  
  
 Windows 런타임 또는 관리되는 형식의 연산자는 형식이 연산자 반환 값의 형식과 동일한 매개 변수를 하나 이상 사용할 수 없습니다.  
  
 다음 샘플에서는 C2395를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2395.cpp  
// compile with: /clr /c  
value struct V {  
   static V operator *(int i, char c);   // C2395  
  
   // OK  
   static V operator *(V v, char c);  
   // or  
   static V operator *(int i, V& rv);  
};  
```