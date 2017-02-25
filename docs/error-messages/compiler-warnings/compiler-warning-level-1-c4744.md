---
title: "컴파일러 경고 (수준 1) C4744 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4744"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4744"
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4744
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var'의 형식이 'file1'과\(와\) 'file2'에서 서로 다릅니다\('type1', 'type2'\).  
  
 두 파일에서 참조하거나 정의한 외부 변수의 형식이 각 파일에서 서로 다릅니다.  이 문제를 해결하려면 형식을 동일하게 정의하거나 한 파일에서 변수 이름을 변경하십시오.  
  
 C4744는 \/GL을 사용하여 파일을 컴파일하는 경우에만 발생합니다.  자세한 내용은 [\/GL\(전체 프로그램 최적화\)](../../build/reference/gl-whole-program-optimization.md)을 참조하십시오.  
  
> [!NOTE]
>  C4744는 일반적으로 C\+\+가 아닌 C 파일에서 발생합니다. C\+\+의 경우 변수 이름은 형식 정보로 데코레이팅되기 때문입니다.  아래 샘플을 C\+\+로 컴파일하면 링커 오류 LNK2019가 발생합니다.  
  
## 예제  
 이 샘플에는 첫 번째 정의가 들어 있습니다.  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## 예제  
 다음 샘플에서는 C4744 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```