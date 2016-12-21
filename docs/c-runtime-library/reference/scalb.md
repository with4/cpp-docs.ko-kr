---
title: "_scalb | Microsoft Docs"
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
  - "_scalb"
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
  - "scalb"
  - "_scalb"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_scalb 함수"
  - "지수 계산"
  - "scalb 함수"
ms.assetid: 148cf5a8-b405-44bf-a1f0-7487adba2421
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _scalb
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2의 거듭제곱으로 배율 인수입니다.  
  
## 구문  
  
```  
double _scalb(  
   double x,  
   long exp   
);  
```  
  
#### 매개 변수  
 `x`  
 배정밀도 부동 소수점 값  
  
 `exp`  
 정수 \(long\) 지수입니다.  
  
## 반환 값  
 성공 하면 지수값을 반환 합니다.  오버 플로\(`x` 의 부호에 따라\) 에서, `_scalb` 는 \+\/\- `HUGE_VAL` 를 반환합니다. `errno` 변수는 `ERANGE` 로 설정 됩니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_scalb` 함수는 `x *` 2exp 의 값을 계산합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_scalb`|\<float.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)