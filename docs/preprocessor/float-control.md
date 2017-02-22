---
title: "float_control | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.float_control"
  - "float_control_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "float_control pragma"
  - "pragma, float_control"
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# float_control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함수의 부동 소수점 동작을 지정합니다.  
  
## 구문  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## Flags  
 `value` *,* `setting` **\[push\]**  
 부동 소수점 동작을 지정합니다.  `value`는 **precise** 또는 **except**가 될 수 있습니다.  자세한 내용은 [\/fp\(부동 소수점 동작 지정\)](../build/reference/fp-specify-floating-point-behavior.md)을 참조하십시오.  `setting`은 **on** 또는 **off**가 될 수 있습니다.  
  
 `value`가 **precise**인 경우 **precise** 및 **except** 설정이 지정됩니다.  **except**는 **precise**가 **on**으로 설정되어 있을 경우 **on**으로만 설정할 수 있습니다.  
  
 선택적 **push** 토큰이 추가되는 경우 `value`에 대한 현재 설정이 내부 컴파일러 스택으로 푸시됩니다.  
  
 **push**  
 현재 `float_control` 설정을 내부 컴파일러 스택으로 푸시합니다.  
  
 **pop**  
 내부 컴파일러 스택 위에서`float_control` 설정을 제거하고 새 `float_control` 설정을 만듭니다.  
  
## 설명  
 **except**가 설정되어 있을 때 `float_control precise`를 해제할 수 없습니다.  마찬가지로 `fenv_access`가 설정되어 있을 때에는 **precise**를 해제할 수 없습니다.  `float_control` pragma를 사용하여 엄격한 모델에서 빠른 모델로 이동하려면 다음 코드를 사용합니다.  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
// The following line is needed on Itanium processors  
#pragma fp_contract(on)  
```  
  
 `float_control` pragma를 사용하여 빠른 모델에서 엄격한 모델로 이동하려면 다음 코드를 사용합니다.  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
// The following line is needed on Itanium processors.  
#pragma fp_contract(off)  
```  
  
 다른 부동 소수점 pragma는 다음과 같습니다.  
  
-   [fenv\_access](../preprocessor/fenv-access.md)  
  
-   [fp\_contract](../preprocessor/fp-contract.md)  
  
## 예제  
 다음 샘플에서는 `float_control` pragma를 사용하여 오버플로 부동 소수점 예외를 catch하는 방법을 보여 줍니다.  
  
```  
// pragma_directive_float_control.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <float.h>  
  
double func( ) {  
   return 1.1e75;  
}  
  
#pragma float_control (except,on)  
  
int main( ) {  
   float u[1];  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);  
   if (err != 0)  
      printf_s("_controlfp_s failed!\n");  
  
   try  {  
      u[0] = func();  
      printf_s ("Fail");     
      return(1);  
   }   
  
   catch (...)  {  
      printf_s ("Pass");  
      return(0);  
   }  
}  
```  
  
  **통과**   
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)