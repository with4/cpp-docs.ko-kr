---
title: "_fpclass, _fpclassf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fpclass"
  - "_fpclassf"
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
  - "fpclass"
  - "_fpclass"
  - "_fpclassf"
  - "math/_fpclass"
  - "float/_fpclass"
  - "math/_fpclassf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fpclass 함수"
  - "부동 소수점 숫자, IEEE 표현"
  - "_fpclass 함수"
  - "_fpclassf 함수"
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _fpclass, _fpclassf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 분류 인수를 나타내는 값을 반환 합니다.  
  
## 구문  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### 매개 변수  
 `x`  
 테스트할 부동 소수점 값입니다.  
  
## 반환 값  
 `_fpclass` 및 `_fpclassf` 함수 인수의 부동 소수점 분류를 나타내는 정수 값을 반환할 `x`합니다. 분류 \< float.h \>에 정의 된 다음 값 중 하나일 수 있습니다.  
  
|값|설명|  
|-------|--------|  
|`_FPCLASS_SNAN`|신호 NaN|  
|`_FPCLASS_QNAN`|자동 NaN|  
|`_FPCLASS_NINF`|음수 무한대\(–INF\)|  
|`_FPCLASS_NN`|정규화된 0이 아닌 음수 값|  
|`_FPCLASS_ND`|비정규화된 음수|  
|`_FPCLASS_NZ`|음수 0\(–0\)|  
|`_FPCLASS_PZ`|양수 0\(\+0\)|  
|`_FPCLASS_PD`|비정규화된 양수|  
|`_FPCLASS_PN`|정규화된 0이 아닌 양수 값|  
|`_FPCLASS_PINF`|양수 무한대\(\+INF\)|  
  
## 설명  
 `_fpclass` 및 `_fpclassf` 함수는 Microsoft 전용입니다. 비슷하기 [fpclassify](../../c-runtime-library/reference/fpclassify.md), 하지만 보다 자세한 인수에 대 한 정보를 반환 합니다.`_fpclassf` 함수는만 사용할 수는 x64 컴파일되면 플랫폼입니다.  
  
## 요구 사항  
  
|함수|필수 헤더|  
|--------|-----------|  
|`_fpclass`|\<float.h\>|  
  
 자세한 호환성 및 규격 정보에 대 한 참조 [호환성](../../c-runtime-library/compatibility.md)합니다.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [isnan, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)