---
title: "컴파일러 경고 (수준 3) C4738 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4738"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4738"
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4738
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

32비트 float 결과를 메모리에 저장하면 성능이 저하될 수 있습니다.  
  
 C4738은 할당, 캐스트, 인수 전달 및 기타 연산의 결과를 반올림해야 함을 경고하거나, 연산에서 레지스터가 부족하여 메모리를 사용해야 했음\(spilling\)을 나타냅니다.  이로 인해 성능이 저하될 수 있습니다.  
  
 반올림하지 않으면서 이 경고를 해결하려면 [\/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md)로 컴파일하거나 `float` 대신 `double`을 사용합니다.  
  
 레지스터가 부족해지는 것을 피하면서 이 경고를 해결하려면 계산의 순서를 변경하고 인라이닝의 사용을 수정하십시오.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4738 오류가 발생하는 경우를 보여 줍니다.  
  
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