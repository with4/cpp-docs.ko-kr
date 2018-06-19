---
title: 컴파일러 오류 C2272 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2272
dev_langs:
- C++
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e969e7cadadf1102dadfb8089a847046731b568f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171769"
---
# <a name="compiler-error-c2272"></a>컴파일러 오류 C2272
'function': 한정자 정적 멤버 함수에 사용할 수 없습니다  
  
 A `static` 멤버 함수는 메모리 내 모델 지정자를 사용 하 여 같은 선언 [const](../../cpp/const-cpp.md) 또는 [휘발성](../../cpp/volatile-cpp.md)에서 이러한 한정자를 사용할 수 없습니다 및 `static` 멤버 함수입니다.  
  
 다음 샘플에서는 C2272 오류가 생성 됩니다.  
  
```  
// C2272.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1() const volatile;   // C2272  func1 is static  
   void func2() const volatile;   // OK  
};  
```