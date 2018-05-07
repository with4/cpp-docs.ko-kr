---
title: 컴파일러 오류 C3866 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3866
dev_langs:
- C++
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da9109e35f3c79d33a4c3439aa58befdbe91068c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3866"></a>컴파일러 오류 C3866
인수 목록이 없습니다. 함수 호출  
  
 비정적 멤버 함수 내에 소멸자 또는 종료자를 호출 하며 인수 목록의 아닙니다.  
  
 다음 샘플에서는 C3866 오류가 생성 됩니다.  
  
```  
// C3866.cpp  
// compile with: /c  
class C {  
   ~C();  
   void f() {  
      this->~C;   // C3866  
      this->~C();   // OK  
   }  
};  
```