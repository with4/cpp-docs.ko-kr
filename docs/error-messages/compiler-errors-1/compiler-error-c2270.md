---
title: 컴파일러 오류 C2270 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2270
dev_langs:
- C++
helpviewer_keywords:
- C2270
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bbafbf35f2aed6d6bddc3298ecfe0e1bf9912e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172374"
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