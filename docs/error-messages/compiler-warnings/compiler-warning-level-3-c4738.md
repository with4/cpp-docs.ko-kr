---
title: 컴파일러 경고 (수준 3) C4738 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4738
dev_langs:
- C++
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50b94cde2f8809b8ce56dc599804d11b8d058166
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291143"
---
# <a name="compiler-warning-level-3-c4738"></a>컴파일러 경고(수준 3) C4738
32비트 float 결과를 메모리에 저장하면 성능이 저하될 수 있습니다.  
  
 C4738을 캐스팅 하는 할당의 결과 인수를 전달 하거나 다른 작업은 반올림 해야 할 수 작업 레지스터가 부족 및 메모리 (모두)를 사용 하는 데 필요한 경고 합니다. 이 성능 손실 될 수 있습니다.  
  
 이 경고를 해결 하려면 반올림 하지를 사용 하 여 컴파일하고 [/fp: fast](../../build/reference/fp-specify-floating-point-behavior.md) 사용 또는 `double` 대신 `float`합니다.  
  
 이 경고를 해결 하려면 레지스터를 사용 하지 않도록, 계산의 순서를 변경 하 고 사용자의 사용 수정할 인라인 처리  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4738 오류가 생성 됩니다.  
  
```  
// C4738.cpp  
// compile with: /c /fp:precise /O2 /W3  
// processor: x86  
#include <stdio.h>  
  
#pragma warning(default : 4738)  
  
float func(float f)  
{  
    return f;  
}  
  
int main()  
{  
    extern float f, f1, f2;  
    double d = 0.0;  
  
    f1 = func(d);  
    f2 = (float) d;  
    f = f1 + f2;   // C4738  
    printf_s("%f\n", f);  
}  
```