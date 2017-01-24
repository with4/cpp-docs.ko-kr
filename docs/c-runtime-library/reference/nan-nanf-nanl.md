---
title: "nan, nanf, nanl | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "nanf"
  - "nan"
  - "nanl"
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
  - "nan"
  - "nanl"
  - "nanf"
dev_langs: 
  - "C++"
ms.assetid: 790e9158-80ab-43e0-8f5a-096198553fd9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# nan, nanf, nanl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Quiet NaN 값을 반환합니다.  
  
## 구문  
  
```  
double nan(    const char* input  ); float nanf(    const char* input  ); long double nanl(    const char* input  );  
```  
  
#### 매개 변수  
 `input`  
 문자열 값입니다.  
  
## 반환 값  
 `nan` 함수는 Quiet NaN 값을 반환합니다.  
  
## 설명  
 `nan` 함수는 Quiet\(비신호\) NaN에 해당하는 부동 소수점 값을 반환합니다.  `input` 값은 무시됩니다.  출력에 NaN이 나타나는 방법에 대한 자세한 내용은 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)를 참조하세요.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`nan`, `nanf`, `nanl`|\<math.h\>|\<cmath\>|  
  
## 해당 .NET Framework 항목  
 [System::Double::NaN](https://msdn.microsoft.com/en-us/library/system.double.nan.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_finite, \_finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [\_fpclass, \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)   
 [isnan, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)