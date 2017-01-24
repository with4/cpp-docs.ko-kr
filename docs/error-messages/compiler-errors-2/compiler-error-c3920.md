---
title: "컴파일러 오류 C3920 | Microsoft Docs"
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
  - "C3920"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3920"
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3920
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator'' : 후위 증가\/감소 WinRT 또는 CLR 연산자를 정의할 수 없습니다. 후위 WinRT 또는 CLR 연산자를 호출하면 후위 의미 체계를 사용하는 해당 전위 WinRT 또는 CLR 연산자\(op\_Increment\/op\_Decrement\)가 호출됩니다.  
  
 Windows 런타임 및 CLR은 후위 연산자를 지원하지 않으며, 사용자 정의 후위 연산자는 허용되지 않습니다.  전위 연산자를 정의할 수 있으며, 그러면 전위 연산자가 전위 증가 작업 및 후위 증가 작업에 모두 사용됩니다.  
  
 다음 샘플에서는 C3920 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3920.cpp  
// compile with: /clr /LD  
public value struct V {  
   static V operator ++(V me, int)  
   // try the following line instead  
   // static V operator ++(V me)  
   {   // C3920  
      me.m_i++;  
      return me;  
   }  
  
   int m_i;  
};  
  
```