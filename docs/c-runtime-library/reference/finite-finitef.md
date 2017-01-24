---
title: "_finite, _finitef | Microsoft Docs"
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
  - "_finite"
  - "_finitef"
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
  - "finite"
  - "_finite"
  - "_finitef"
  - "math/_finite"
  - "math/_finitef"
  - "float/_finite"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "finite 함수"
  - "_finite 함수"
  - "_finitef 함수"
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _finite, _finitef
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 값이 유한인지 확인합니다.  
  
## 구문  
  
```  
int _finite(   
   double x   
);  
  
int _finitef(   
   float x   
); /* x64 and ARM/ARM64 only */  
```  
  
#### 매개 변수  
 `x`  
 테스트할 부동 소수점 값입니다.  
  
## 반환 값  
 *x* 인수가 유한인 경우, 즉 –INF \< `x` \< \+INF인 경우 `_finite` 및 `_finitef` 둘 다 0이 아닌 값을 반환합니다. 인수가 무한이거나 NAN이면 0을 반환합니다.  
  
## 설명  
 `_finite` 및 `_finitef` 함수는 Microsoft 전용입니다.`_finitef` 함수는 x86, ARM, 또는 ARM64 용으로 컴파일된 경우에 사용할 수 있는 플랫폼만 합니다.  
  
## 요구 사항  
  
|함수|필수 헤더\(C\)|필수 헤더\(C\+\+\)|  
|--------|----------------|--------------------|  
|`_finite`|\<float.h\> 또는 \<math.h\>|\<float.h\>, \<math.h\>, \<cfloat\> 또는 \<cmath\>|  
|`_finitef`|\<math.h\>|\<math.h\> 또는 \<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 [System::Double::IsInfinity](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [isnan, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [\_fpclass, \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)