---
title: 컴파일러 경고 (수준 4) C4816 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4816
dev_langs:
- C++
helpviewer_keywords:
- C4816
ms.assetid: 60f730ae-d942-4db9-ab97-41d4a874d8da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74386e980171ce1b54c8256ad505b363df7830d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4816"></a>컴파일러 경고(수준 4) C4816
'param': 매개 변수에 크기가 0인 배열이 있으면 잘리게 됩니다(개체가 참조로 전달된 경우 제외).  
  
 크기가 0인 배열을 가진 개체에 대한 매개 변수가 참조로 전달되지 않았습니다. 개체가 전달될 때 배열이 복사되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4816을 생성합니다.  
  
```  
// C4816.cpp  
// compile with: /W4  
#include <stdio.h>  
  
extern "C" int printf_s(const char *, ...);  
  
#pragma warning(disable : 4200)  
  
struct S1  
{  
    int i;  
    char cArr[];  
};  
  
void TestErr(S1 s1)   // C4816 param with zero-array   
                      // not passed by reference  
{  
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);  
}  
  
void TestOk(S1 &s1)  
{  
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);  
}  
  
int main()  
{  
    S1 myS_1 = { 6, 'a', 'b', 'c' };  
    TestErr(myS_1);  
    TestOk(myS_1);  
}  
```