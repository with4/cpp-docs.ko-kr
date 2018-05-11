---
title: 컴파일러 오류 C3920 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3920
dev_langs:
- C++
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ced0a0f8fa2b6694de4dd901d71f6721e12493b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3920"></a>컴파일러 오류 C3920
' 연산자 ': 후 위 증가/감소 WinRT 또는 CLR 연산자를 호출 하는 후 위 정의할 수 없습니다 WinRT 또는 CLR 연산자는 해당 접두사를 호출 하는 WinRT 또는 CLR 연산자 (op_Increment/op_decrement)가 후 위 의미 체계와  
  
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