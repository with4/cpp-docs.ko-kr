---
title: "fenv_access | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.fenv_access"
  - "fenv_access_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenv_access pragma"
  - "pragma, fenv_access"
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# fenv_access
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

플래그 테스트 및 모드 변경 내용을 변경할 수 있는 최적화를 비활성화\(ON\)하거나 활성화\(OFF\)합니다.  
  
## 구문  
  
```  
#pragma fenv_access [ON | OFF]  
```  
  
## 설명  
 기본적으로 `fenv_access`는 OFF로 설정됩니다.  
  
 부동 소수점 동작에 대한 자세한 내용은 [\/fp\(부동 소수점 동작 지정\)](../build/reference/fp-specify-floating-point-behavior.md)를 참조하십시오.  
  
 `fenv_access`를 적용할 수 있는 최적화 종류는 다음과 같습니다.  
  
-   전역 공통 하위 식 제거  
  
-   코드 이동  
  
-   상수 정리  
  
 다른 부동 소수점 pragma는 다음과 같습니다.  
  
-   [float\_control](../preprocessor/float-control.md)  
  
-   [fp\_contract](../preprocessor/fp-contract.md)  
  
## 예제  
  
```  
// pragma_directive_fenv_access_x86.cpp  
// compile with: /O2  
// processor: x86  
#include <stdio.h>  
#include <float.h>   
#include <errno.h>  
#pragma fenv_access (on)  
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
  **out\=9.999999776482582e\-003**   
## 예제  
 다음 샘플은 Itanium 프로세서에 대한 출력 파일을 생성하는 컴파일러용입니다.  **\/fp:precise**는 중간 결과를 확장된 정밀도로 유지합니다. 여기서는 FLT\_MAX\(3.402823466e\+38F\)보다 큰 값을 계산할 수 있으며, 해당 합계의 결과는 수동으로 계산할 때와 같이 1.0이 됩니다.  **\/fp:strict**는 중간 결과를 소스 정밀도\(부동\)로 유지하므로 첫 번째 더하기에서 무한 값이 생성되어 식 전체에서 유지됩니다.  
  
```  
// pragma_directive_fenv_access_IPF.cpp  
// compile with: /O2 /fp:precise  
// processor: IPF  
// compiling with /fp:precise prints 1.0F  
// compile with /fp:strict to print infinity  
  
#include <stdio.h>  
float arr[5] = {3.402823465e+38F,   
               3.402823462e+38F,  
               3.402823464e+38F,  
               3.402823463e+38F,  
               1.0F};  
  
int main() {  
   float sum = 0;  
   sum = arr[0] + arr[1] - arr[2] - arr[3] + arr[4];  
   printf_s("%f\n", sum);  
}  
```  
  
  **1.000000**   
## 예제  
 위의 샘플에서 `#pragma fenv_access (on)`을 주석 처리할 때는 컴파일러가 컴파일 타임 계산\(컨트롤 모드를 사용하지 않음\)을 수행하므로 출력이 달라진다는 점에 주의해야 합니다.  
  
```  
// pragma_directive_fenv_access_2.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>   
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
  **out\=1.000000000000000e\-002**   
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)