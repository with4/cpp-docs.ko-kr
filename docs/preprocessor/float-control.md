---
title: float_control | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
dev_langs: C++
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 821890c7fdb719b5ab320588476bd1ebb73793ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="floatcontrol"></a>float_control
함수의 부동 소수점 동작을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## <a name="flags"></a>플래그  
 `value``setting` **[푸시]**  
 부동 소수점 동작을 지정합니다. `value`수 **정확한** 또는 **제외 하 고**합니다. 자세한 내용은 [/fp(부동 소수점 동작 지정)](../build/reference/fp-specify-floating-point-behavior.md)를 참조하세요. `setting`수 **에** 또는 **오프**합니다.  
  
 경우 `value` 은 **정확한**에 대 한 설정을 **정확 하 게** 및 **제외 하 고** 지정 된 합니다. **제외 하 고** 로 설정할 수 **에** 때 **정확한** 도로 설정 **에**합니다.  
  
 경우 선택적 **푸시** 토큰이 추가 되 면 현재 설정에 대 한 `value` 내부 컴파일러 스택에 푸시됩니다.  
  
 **push**  
 현재 `float_control` 설정을 내부 컴파일러 스택으로 푸시합니다.  
  
 **pop**  
 제거는 `float_control` 내부 컴파일러 스택 맨 위에서 설정 하 고이 새 `float_control` 설정 합니다.  
  
## <a name="remarks"></a>설명  
 설정할 수 없으며 `float_control precise` 설정 되어 있을 때 **제외 하 고** 켜져 있습니다. 마찬가지로, **정확한** 해제할 수 없는 경우 `fenv_access` 켜져 있습니다. `float_control` pragma를 사용하여 엄격한 모델에서 빠른 모델로 이동하려면 다음 코드를 사용합니다.  
  
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
  
-   [fenv_access](../preprocessor/fenv-access.md)  
  
-   [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>예  
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
  
```Output  
Pass  
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)