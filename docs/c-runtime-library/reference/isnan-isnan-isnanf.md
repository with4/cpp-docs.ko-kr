---
title: "isnan, _isnan, _isnanf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isnan"
  - "_isnanf"
  - "isnan"
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
  - "_isnan"
  - "isnan"
  - "math/isnan"
  - "math/_isnan"
  - "math/_isnanf"
  - "_isnanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NAN(숫자가 아님)"
  - "_isnan 함수"
  - "IEEE 부동 소수점 표시"
  - "숫자가 아님(NAN)"
  - "isnan 함수"
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# isnan, _isnan, _isnanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 값이 NAN \(숫자가\)를 테스트 합니다.  
  
## 구문  
  
```  
int isnan(  
   /* floating-point */ x   
); /* C-only macro */  
  
int _isnan(  
   double x   
);  
  
int _isnanf(  
   float x  
); /* x64 only */  
  
template <class T>  
bool isnan(  
   T x  
) throw(); /* C++ only */  
```  
  
#### 매개 변수  
 *x*  
 테스트할 부동 소수점 값입니다.  
  
## 반환 값  
 C에서는 `isnan` 매크로 및 `_isnan` 및 `_isnanf` 경우 함수는 0이 아닌 값을 반환 인수 `x` nan; 그렇지 않으면 0을 반환할 수 있습니다.  
  
 C \+ \+에서는 `isnan` 템플릿 함수의 반환 `true` 경우 인수 `x` nan; 반환 그렇지 않으면 `false`합니다.  
  
## 설명  
 C `isnan` 매크로 및 `_isnan` 및 `_isnanf` 부동 소수점 값을 테스트 하는 함수 *x*, 를 하면 0이 아닌 값을 반환 *x* 아닙니다 번호 \(NAN\) 값입니다. NAN에는 지정된 된 형식에 대 한 IEEE 754 부동 소수점 형식에서 부동 소수점 작업의 결과 표현할 수 없는 경우 생성 됩니다. 출력에 NAN이 나타나는 방법에 대 한 정보를 참조 하십시오. [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)합니다.  
  
 C \+ \+ 파일로 컴파일된 경우는 `isnan` 매크로 정의 하지 않으면 서 `isnan` 템플릿 함수 대신 정의 됩니다. 형식의 값을 반환 `bool` 정수 대신 합니다.  
  
 `_isnan` 및 `_isnanf` 함수는 Microsoft 전용입니다.`_isnanf` 기능은 x64 용으로 컴파일된 경우에 사용할 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더\(C\)|필수 헤더\(C\+\+\)|  
|--------|----------------|--------------------|  
|`isnan`, `_isnanf`|\<math.h\>|\<math.h\> 또는 \<cmath\>|  
|`_isnan`|\<float.h\>|\< float.h \> 또는 \< cfloat \>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_finite, \_finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [\_fpclass, \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)