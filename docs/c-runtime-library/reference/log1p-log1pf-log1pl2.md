---
title: "log1p, log1pf, log1pl2 | Microsoft Docs"
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
  - "log1p"
  - "log1pf"
  - "log1pl"
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
  - "log1p"
  - "log1pf"
  - "log1pl"
  - "math/log1p"
  - "math/log1pf"
  - "math/log1pl"
helpviewer_keywords: 
  - "log1p 함수"
  - "log1pf 함수"
  - "log1pl 함수"
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# log1p, log1pf, log1pl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

1을 더한 지정된 된 값의 자연 로그를 계산합니다.  
  
## 구문  
  
```  
double log1p(  
   double x  
);  
  
float log1p(  
   float x  
); //C++ only  
  
long double log1p(  
   long double x  
); //C++ only  
  
float log1pf(  
   float x  
);  
  
long double log1pl(  
   long double x  
);  
  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 인수입니다.  
  
## 반환 값  
 성공 하는 경우의 자연 \(밑이 e 인\) 로그를 반환 \(`x`\+ 1\).  
  
 그렇지 않은 경우 반환할 수 있습니다 다음 값 중 하나:  
  
|입력|결과|SEH 예외|errno|  
|--------|--------|------------|-----------|  
|\+ inf|\+ inf|||  
|Denormals|입력과 동일|언더플로||  
|±0|입력과 동일|||  
|\-1|\-inf|DIVBYZERO|ERANGE|  
|\< \-1|nan|잘못 되었습니다.|EDOM|  
|\-inf|nan|잘못 되었습니다.|EDOM|  
|±SNaN|입력과 동일|잘못 되었습니다.||  
|무한 ±QNaN|입력과 동일|||  
  
 `errno` 값이를 erange로 설정 하는 경우 `x` \=\-1입니다.`errno` 경우 EDOM에 값이 설정 `x` \<에서 1입니다.  
  
## 설명  
 `log1p` 함수는 로그를 사용 하 여 보다 정확한 수 있습니다 \(`x`\+ 1\) 0에 가까우면 x 표시 되는 경우.  
  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `log1p` 및 float 및 long double 형식을 반환 하 합니다. C 프로그램에서 `log1p` 항상 걸리고 double 값을 반환 합니다.  
  
 경우 `x` 는 자연 숫자의 계승값의 로그를 반환 하는이 함수 \(`x`\-1\).  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`log1p`, `log1pf`,  `log1pl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)