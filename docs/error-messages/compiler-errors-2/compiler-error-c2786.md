---
title: 컴파일러 오류 C2786 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2786
dev_langs:
- C++
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29fd0d8cf22be29757abd775e1bb844cb1a1bfbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2786"></a>컴파일러 오류 C2786
'type': __uuidof의 피연산자가 잘못 되었습니다.  
  
 [__uuidof](../../cpp/uuidof-operator.md) 연산자는 연결 된 GUID 또는 사용자 정의 형식의 개체와 사용자 정의 형식을 사용 합니다.  가능한 원인:  
  
1.  인수는 사용자 정의 형식이 아닙니다.  
  
2.  `__uuidof` 인수에서 GUID를 추출할 수 없습니다.  
  
 다음 샘플에서는 C2786 오류가 생성 됩니다.  
  
```  
// C2786.cpp  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
  
int main() {  
   __uuidof(int);   // C2786  
   __uuidof(int *);   // C2786  
   __uuidof(A **);   // C2786  
  
   // no error  
   __uuidof(A);  
   __uuidof(A *);  
   __uuidof(A &);  
   __uuidof(A[]);  
  
   int i;  
   int *pi;  
   A **ppa;  
  
   __uuidof(i);      // C2786  
   __uuidof(pi);     // C2786  
   __uuidof(ppa);    // C2786  
}  
```