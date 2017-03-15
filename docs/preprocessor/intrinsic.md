---
title: "내장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "intrinsic_CPP"
  - "vc-pragma.intrinsic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "내장 pragma"
  - "pragma, 내장"
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 내장
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

pragma의 인수 목록에 지정된 함수에 대한 호출을 내장 함수로 지정합니다.  
  
## 구문  
  
```  
  
#pragma intrinsic( function1 [, function2, ...] )  
```  
  
## 설명  
 **intrinsic** pragma는 함수에 알려진 동작이 있음을 컴파일러에 알립니다.  컴파일러는 함수를 호출할 수 있으며 성능을 개선할 수 있는 경우 함수 호출을 인라인 명령으로 바꾸지 않을 수 있습니다.  
  
 아래에 내장 형식의 라이브러리 함수가 나와 있습니다.  **intrinsic** pragma는 표시된 후 지정한 내장 함수를 포함하는 첫 번째 함수 정의에서 적용됩니다.  이 pragma는 동일한 내장 함수를 지정하는 **function** pragma가 표시되는 위치 또는 소스 파일의 끝까지 계속 적용됩니다.  **intrinsic** pragma는 전역 수준에서 함수 정의 외부에만 사용할 수 있습니다.  
  
 다음 함수는 내장 형식이며, 내장 형식은 [\/Oi](../build/reference/oi-generate-intrinsic-functions.md)를 지정할 때 사용됩니다.  
  
|||||  
|-|-|-|-|  
|[\_disable](../intrinsics/disable.md)|[\_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|  
|[\_enable](../intrinsics/enable.md)|[\_outpw](../c-runtime-library/outp-outpw-outpd.md)|[labs](../misc/labs-llabs.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|  
|[\_inp](../c-runtime-library/inp-inpw-inpd.md)|[\_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|  
|[\_inpw](../c-runtime-library/inp-inpw-inpd.md)|[\_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||  
|[\_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[\_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||  
|[\_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||  
  
 내장 함수를 사용하는 프로그램은 함수 호출의 오버헤드가 없기 때문에 빠르게 실행되지만 추가 코드가 생성되므로 프로그램이 커질 수 있습니다.  
  
 **x86 전용**  
  
 \_disable 및 \_enable 내장 함수는 인터럽트를 비활성화\/활성화하기 위한 커널 모드 명령을 생성하며 커널 모드 드라이버에서 유용할 수 있습니다.  
  
## 예제  
 "cl \-c \-FAs sample.c"를 사용하여 다음 코드를 명령줄에서 컴파일한 다음 sample.asm을 찾아 이러한 내장 함수가 x86 명령 CLI 및 STI로 바뀌었는지 확인하십시오.  
  
```  
// pragma_directive_intrinsic.cpp  
// processor: x86  
#include <dos.h>   // definitions for _disable, _enable  
#pragma intrinsic(_disable)  
#pragma intrinsic(_enable)  
void f1(void) {  
   _disable();  
   // do some work here that should not be interrupted  
   _enable();  
}  
int main() {  
}  
```  
  
 **x86 전용 종료**  
  
 아래에 나와 있는 부동 소수점 함수는 실제 내장 형식을 포함하지 않습니다.  대신 인수를 프로그램 스택으로 푸시하지 않고 부동 소수점 칩으로 직접 전달하는 버전이 있습니다.  
  
|||||  
|-|-|-|-|  
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)||  
  
 아래에 나와 있는 부동 소수점 함수는 [\/Oi](../build/reference/oi-generate-intrinsic-functions.md), [\/Og](../build/reference/og-global-optimizations.md) 및 [\/fp:fast](../build/reference/fp-specify-floating-point-behavior.md)\(또는 \/Og: [\/Ox](../build/reference/ox-full-optimization.md), [\/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md) 및 \/O2를 포함하는 모든 옵션\)를 지정하는 경우 실제 내장 형식을 포함합니다.  
  
|||||  
|-|-|-|-|  
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)||||  
  
 [\/fp:strict](../build/reference/fp-specify-floating-point-behavior.md) 또는 [\/Za](../build/reference/za-ze-disable-language-extensions.md)를 사용하여 실제 내장 부동 소수점 옵션 생성을 재정의할 수 있습니다.  이 경우에는 함수가 인수를 프로그램 스택으로 푸시하는 대신 부동 소수점 칩으로 직접 전달하는 라이브러리 루틴으로 생성됩니다.  
  
 소스 텍스트 블록에 대해 내장 함수를 활성화\/비활성화하는 방법에 대한 자세한 내용과 예제는 [\# pragma 함수](../preprocessor/function-c-cpp.md)를 참조하십시오.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)