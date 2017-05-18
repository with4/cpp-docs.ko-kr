---
title: "컴파일러 경고 (수준 3) C4738 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4738
dev_langs:
- C++
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ce2db890b7b90eedf5b4456e875a06f8f92b0289
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-warning-level-3-c4738"></a>컴파일러 경고(수준 3) C4738
32비트 float 결과를 메모리에 저장하면 성능이 저하될 수 있습니다.  
  
 C4738을 캐스팅 하는 할당의 결과 인수를 전달 또는 기타 작업을 반올림할 해야 할 수 작업 레지스터가 부족 및 메모리 (모두)를 사용 하는 데 필요한 경고 합니다. 이 성능 손실 될 수 있습니다.  
  
 이 경고를 해결 하려면 반올림 하지를 사용 하 여 컴파일하고 [/fp: fast](../../build/reference/fp-specify-floating-point-behavior.md) 사용 또는 `double` 대신 `float`합니다.  
  
 이 경고를 해결 하려면 레지스터를 사용 하지 않도록, 계산의 순서를 변경 하 고 사용자의 사용 수정할 인라인 처리  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 참조 [기본적으로 해제 되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)합니다.  
  
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
