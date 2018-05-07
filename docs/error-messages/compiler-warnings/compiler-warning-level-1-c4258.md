---
title: 컴파일러 경고 (수준 1) C4258 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4258
dev_langs:
- C++
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08a182ed592119fd52247737988810f9ca66b45c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4258"></a>컴파일러 경고(수준 1) C4258
'variable':에서 정의 된 루프 무시 됩니다. 사용 되는 바깥쪽 범위에서 정의 "  
  
 아래 [/Ze](../../build/reference/za-ze-disable-language-extensions.md) 및 [/zc: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)에 정의 된 변수는 [에 대 한](../../cpp/for-statement-cpp.md) 루프 후 범위를 벗어나는 **에 대 한** 루프가 종료 합니다. 바깥쪽 루프에서 정의한 루프 변수와 동일한 이름 가진 변수를 포함 하는 범위에서 다시 사용 하는 경우이 경고가 발생 된 **에 대 한** 루프입니다. 예를 들어:  
  
```  
// C4258.cpp  
// compile with: /Zc:forScope /W1  
int main()  
{  
   int i;  
   {  
      for (int i =0; i < 1; i++)  
         ;  
      i = 20;   // C4258 i (in for loop) has gone out of scope  
   }  
}  
```