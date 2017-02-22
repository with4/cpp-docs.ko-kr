---
title: "fpclassify | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fpclassify"
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
apitype: "HeaderDef"
f1_keywords: 
  - "fpclassify"
  - "math/fpclassify"
helpviewer_keywords: 
  - "fpclassify 매크로"
  - "fpclassify 함수"
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# fpclassify
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 인수 분류를 반환합니다.  
  
## 구문  
  
```  
int fpclassify(   
   /* floating-point */ x   
);  
  
int fpclassify(   
   float x   
); // C++ only  
  
int fpclassify(   
   double x   
); // C++ only  
  
int fpclassify(   
   long double x   
); // C++ only  
  
```  
  
#### 매개 변수  
 `x`  
 테스트할 부동 소수점 값입니다.  
  
## 반환 값  
 `fpclassify` 인수의 부동 소수점 클래스를 나타내는 정수 값을 반환 `x`합니다. 이 테이블에서 반환 된 가능한 값이 나와 `fpclassify`, \< h. h \>에 정의 된 합니다.  
  
|값|설명|  
|-------|--------|  
|`FP_NAN`|자동, 신호, 또는 결정 되지 않은 NaN|  
|`FP_INFINITE`|양 또는 음의 무한대|  
|`FP_NORMAL`|양수 또는 음수 정규화 된 0이 아닌 값|  
|`FP_SUBNORMAL`|비 정규화 된 양수 또는 음수 값|  
|`FP_ZERO`|양수 또는 음수 값이 0 이면|  
  
## 설명  
 C에서 `fpclassify` 는 매크로, c \+ \+에서는 `fpclassify` 유형의 인수를 사용 하 여 오버 로드 된 함수는 `float`, `double`, 또는 `long double`합니다. 두 경우 모두에서 반환 되는 값에는 모든 중간 표현 아닌 인수 식의 효과적인 형식에 따라 다릅니다. 예를 들어 일반 `double` 또는 `long double` 값 수는 무한대 될, 비정상적인, 또는 0 값으로 변환 하는 경우는 `float`합니다.  
  
## 요구 사항  
  
|기능\/매크로|필수 헤더\(C\)|필수 헤더\(C\+\+\)|  
|-------------|----------------|--------------------|  
|`fpclassify`|\<math.h\>|\<math.h\> 또는 \<cmath\>|  
  
 `fpclassify` 매크로 및 `fpclassify` 함수는 C99 및 C \+ \+ 11 사양에 따라야 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [isnan, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)