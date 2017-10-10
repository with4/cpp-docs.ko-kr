---
title: "컴파일러 오류 C2270 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2270
dev_langs:
- C++
helpviewer_keywords:
- C2270
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bc380d8a44e61ac0f709b8440d788d12f3795922
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2270"></a>컴파일러 오류 C2270
'function': 한정자 비멤버 함수에 사용할 수 없습니다  
  
 비멤버 함수가 선언 되 [const](../../cpp/const-cpp.md), [휘발성](../../cpp/volatile-cpp.md), 또는 다른 메모리 모델 한정자입니다.  
  
 다음 샘플에서는 C2270 오류가 생성 됩니다.  
  
```  
// C2270.cpp  
// compile with: /c  
void func1(void) const;   // C2270, nonmember function  
  
void func2(void);  
  
class CMyClass {  
public:  
   void func2(void) const;  
};  
```
