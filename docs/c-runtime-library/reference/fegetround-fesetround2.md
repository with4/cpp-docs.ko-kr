---
title: "fegetround, fesetround2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fegetround"
  - "fesetround"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "fegetround"
  - "fesetround"
  - "fenv/fegetround"
  - "fenv/fesetround"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fegetround 함수"
  - "fesetround 함수"
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# fegetround, fesetround
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 부동 소수점 반올림 모드를 가져오거나 설정합니다.  
  
## 구문  
  
```  
int fegetround(void);  
  
int fesetround(  
   int round_mode  
);   
```  
  
#### 매개 변수  
 `round_mode`  
 부동 소수점 반올림 매크로 중 하나로 설정할 반올림 모드입니다. 값이 부동 소수점 반올림 매크로 중 하나와 같지 않은 경우 반올림 모드가 변경되지 않습니다.  
  
## 반환 값  
 성공 시 `fegetround`는 반올림 모드를 부동 소수점 반올림 매크로 값 중 하나로 반환합니다. 현재 반올림 모드를 확인할 수 없는 경우 음수 값이 반환됩니다.  
  
 성공 시 `fesetround`는 0을 반환합니다. 그렇지 않으면 0이 아닌 값이 반환됩니다.  
  
## 주의  
 부동 소수점 연산에는 몇 가지 반올림 모드 중 하나를 사용할 수 있습니다. 이러한 모드에 따라 결과가 저장될 때 부동 소수점 연산의 결과가 반올림되는 방향이 제어됩니다. 다음은 \<fenv.h\>에 정의된 부동 소수점 반올림 매크로의 이름 및 동작입니다.  
  
|매크로|설명|  
|---------|--------|  
|FE\_DOWNWARD|음의 무한대로 반올림합니다.|  
|FE\_TONEAREST|가장 가까운 값으로 반올림합니다.|  
|FE\_TOWARDZERO|0으로 반올림합니다.|  
|FE\_UPWARD|양의 무한대로 반올림합니다.|  
  
 FE\_TONEAREST의 기본 동작은 표현 가능한 값의 중간 결과를 짝수\(0\) 최하위 비트를 갖는 가장 가까운 값으로 반올림하는 것입니다.  
  
 현재 반올림 모드는 다음 작업을 영향을 줍니다.  
  
-   문자열 변환  
  
-   상수 식 외부의 부동 소수점 산술 연산자 결과  
  
-   `rint` 및 `nearbyint`와 같은 라이브러리 반올림 함수  
  
-   표준 라이브러리 수학 함수의 값을 반환합니다.  
  
 현재 반올림 모드는 다음 작업에 영향을 주지 않습니다.  
  
-   `trunc`, `ceil`, `floor`, 및 `lround` 라이브러리 함수  
  
-   항상 0으로 반올림되는 부동 소수점\-정수 암시적 캐스팅 및 변환  
  
-   항상 가장 가까운 값으로 반올림되는 상수 식의 부동 소수점 산술 연산자 결과  
  
 이러한 함수를 사용하려면 호출 전에 `#pragma fenv_access(on)` 지시문을 사용하여 액세스를 방지할 수 있는 부동 소수점 최적화를 꺼야 합니다. 자세한 내용은 [fenv\_access](../../preprocessor/fenv-access.md)을 참조하세요.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`fegetround`, `fesetround`|\<fenv.h\>|\<cfenv\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [nearbyint, nearbyintf, nearbyintl](../../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)   
 [rint, rintf, rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](../../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)