---
title: "ilogb, ilogbf, ilogbl2 | Microsoft Docs"
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
  - "ilogb"
  - "ilogbf"
  - "ilogbl"
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
  - "ilogb"
  - "ilogbf"
  - "ilogbl"
  - "math/ilogb"
  - "math/ilogbf"
  - "math/ilogbl"
helpviewer_keywords: 
  - "ilogb 함수"
  - "ilogbf 함수"
  - "ilogbl 함수"
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# ilogb, ilogbf, ilogbl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 된 값의 비편향된 밑이 2 인 지 수를 나타내는 정수를 검색 합니다.  
  
## 구문  
  
```  
int ilogb(  
   double x  
);  
  
int ilogb(  
   float x  
); //C++ only  
  
int ilogb(  
   long double x  
); //C++ only  
  
int ilogbf(  
   float x  
);  
  
int ilogbl(  
   long double x  
);  
  
```  
  
#### 매개 변수  
 \[in\] `x`  
 지정된 값입니다.  
  
## 반환 값  
 성공 하는 경우의 밑이 2 인 지 수를 반환 `x` signed로 `int` 값입니다.  
  
 그렇지 않으면 \< h. h \>에 정의 된 다음 값 중 하나를 반환 합니다.  
  
|입력|결과|  
|--------|--------|  
|±0|FP\_ILOGB0|  
|±inf, ±nan 정해 지지 않은|FP\_ILOGBNAN|  
  
 오류를 보고에 지정 된 대로 [\_matherr](../../c-runtime-library/reference/matherr.md)합니다.  
  
## 주의  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `ilogb` 및 float 및 long double 형식을 반환 하 합니다. C 프로그램에서 `ilogb` 항상 걸리고 double 값을 반환 합니다.  
  
 이 함수를 호출 하는 것은 해당 하는 호출 비슷합니다 `logb` 함수를 다음 반환 값을 캐스팅 `int`합니다.  
  
## 요구 사항  
  
|루틴|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`ilogb`, `ilogbf`,  `ilogbl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [logb, logbf, logbl, \_logb, \_logbf](../../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)