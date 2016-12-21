---
title: "_set_SSE2_enable | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_SSE2_enable"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_SSE2_enable"
  - "set_SSE2_enable"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_SSE2_enable 함수"
  - "스트리밍 SIMD 확장 2 지침"
  - "set_SSE2_enable 함수"
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_SSE2_enable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CRT 수학 루틴의 [Streaming SIMD Extensions 2](http://msdn.microsoft.com/ko-kr/f98440eb-73a9-4f96-b203-ac41bb6701ea) \(SSE2\) 명령어의 사용을 적용 또는 미적용합니다. \(x64 아키텍쳐에서는 SSE2가 기본적으로 적용되기 때문에 이 기능은 사용 가능하지 않습니다.\)  
  
## 구문  
  
```  
int _set_SSE2_enable(  
   int flag  
);  
```  
  
#### 매개 변수  
 `flag`  
 SSE2 구현을 사용하려면 1, SSE2 구현을 사용하지 않으려면 0입니다.  기본적으로, 지원되는 프로세서에서 SSE2 구현은 활성화됩니다.  
  
## 반환 값  
 SSE2 구현이 활성화되면 0이 아닌 값이며, SSE2 구현이 비활성화되면 0입니다.  
  
## 설명  
 다음 함수는 SSE2 구현을 포함하기 때문에 `_set_SSE2_enable`를 이용하여 활성화시킬 수 있습니다.  
  
-   [atan](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)  
  
-   [ceil](../../c-runtime-library/reference/ceil-ceilf-ceill.md)  
  
-   [exp](../../c-runtime-library/reference/exp-expf.md)  
  
-   [floor](../../c-runtime-library/reference/floor-floorf-floorl.md)  
  
-   [log](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [log10](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [modf](../../c-runtime-library/reference/modf-modff-modfl.md)  
  
-   [pow](../../c-runtime-library/reference/pow-powf-powl.md)  
  
 SSE2 중간 값은 64비트 부동 소수점 값이지만 기본 구현 중간 값은 80비트 부동 소수점 값이기 때문에 이러한 함수의 SSE2 구현은 기본 구현과는 약간 다른 결과를 낼 수 있습니다.  
  
> [!NOTE]
>  프로젝트를 컴파일하기 위하여 [\/Oi \(내장 함수\)](../../build/reference/oi-generate-intrinsic-functions.md) 컴파일러 옵션을 사용하는 경우, `_set_SSE2_enable`은 아무런 영향을 주지 않을 수 있습니다.  `/Oi` 컴파일러 옵션은 CRT 호출을 대체하는 컴파일러에 내장 함수를 사용하는 권한을 부여합니다. 이 동작은 `_set_SSE2_enable` 효과를 무효로 합니다.  `/Oi`가 `_set_SSE2_enable`를 무시하지 않도록 보장하기를 원한다면, 프로젝트를 컴파일하는 데에 `/Oi-`을 사용하십시오.  `/Oi`를 내포하는 다른 컴파일러 스위치를 사용하는 것도 좋습니다.  
  
 SSE2 구현은 모든 예외가 마스크된 경우에만 사용됩니다.  예외를 마스크하기 위하여 [\_control87, \_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md)을 사용합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_set_SSE2_enable`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_set_SSE2_enable.c  
// processor: x86  
#include <math.h>  
#include <stdio.h>  
  
int main()  
{  
   int i = _set_SSE2_enable(1);  
  
   if (i)  
      printf("SSE2 enabled.\n");  
   else  
      printf("SSE2 not enabled; processor does not support SSE2.\n");  
}  
```  
  
 **Output**  
  
 `SSE2 enabled.`  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)