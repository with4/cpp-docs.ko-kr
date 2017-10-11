---
title: "컴파일러 오류 C2658 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2658
dev_langs:
- C++
helpviewer_keywords:
- C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 252c543b8ba4dfc470bc1641a3d91c3dfc06177d
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2658"></a>컴파일러 오류 C2658
'member': 익명 구조체/공용 구조체에 재정의  
  
 두 개의 익명 구조체 또는 공용 구조체 멤버 선언을 같은 식별자를 가진 했지만 다른 형식이 포함 되어 있습니다. 아래 [/Za](../../build/reference/za-ze-disable-language-extensions.md), 같은 식별자와 형식 멤버에 대해이 오류를 발생 하기도 합니다.  
  
 다음 샘플에서는 C2658 오류가 생성 됩니다.  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```
