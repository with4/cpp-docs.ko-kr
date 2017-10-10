---
title: "컴파일러 오류 C2571 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2571
dev_langs:
- C++
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8bfb4f9af849efea2fa3aa8a84a57f1cfb4cd502
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2571"></a>컴파일러 오류 C2571
'function': 가상 함수에 ' union' 될 수 없습니다  
  
 공용 구조체는 가상 함수 선언 됩니다. 클래스 또는 구조체에만 가상 함수를 선언할 수 있습니다.  가능한 해결 방법:  
  
1.  클래스 또는 구조체를 공용 구조체를 변경 합니다.  
  
2.  비가상 함수를 확인 합니다.  
  
 다음 샘플에서는 C2571 오류가 생성 됩니다.  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```
