---
title: "컴파일러 오류 C3280 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3280
dev_langs:
- C++
helpviewer_keywords:
- C3280
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4534ac1df55ed5e0810cd0a8d5ce54a5081b929e
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3280"></a>컴파일러 오류 C3280
'class': 관리되는 형식의 멤버-함수는 관리되지 않는 함수로 컴파일할 수 없습니다.  
  
 관리되는 클래스 멤버 함수를 관리되지 않는 함수로 컴파일할 수 없습니다.  
  
 다음 샘플에서는 C3280을 생성합니다.  
  
```  
// C3280_2.cpp  
// compile with: /clr  
ref struct A {  
   void func();  
};  
  
#pragma managed(push,off)  
  
void A::func()   // C3280  
{  
}  
  
#pragma managed(pop)  
```  

