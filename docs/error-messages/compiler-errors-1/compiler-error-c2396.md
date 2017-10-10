---
title: "컴파일러 오류 C2396 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2396
dev_langs:
- C++
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 20eca11d402265bbc81d61a8079ae9975cceef67
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2396"></a>컴파일러 오류 C2396
' your_type:: operator'type ': WinRT 또는 CLR 사용자 정의 변환 functionnot를 유효 합니다. 다음에서 변환되거나 다음으로 변환해야 합니다. 'T^', 'T^%', 'T^&'(T = 'your_type')  
  
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
