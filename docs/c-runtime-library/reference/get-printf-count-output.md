---
title: "_get_printf_count_output | Microsoft Docs"
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
  - "_get_printf_count_output"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_printf_count_output"
  - "_get_printf_count_output"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "%n 형식"
  - "_get_printf_count_output 함수"
  - "get_printf_count_output 함수"
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_printf_count_output
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)군 함수가 `%n` 형식을 지원하는지 아닌지를 가리킵니다.  
  
## 구문  
  
```  
int _get_printf_count_output();  
```  
  
## 반환 값  
 `%n`가 지원되는 경우 0이 아닌 값을, `%n`가 지원되지 않는 경우 0입니다.  
  
## 설명  
 `%n`가 지원되지 않는 경우\(기본\), 모든 `printf` 함수의 형식 문자열에서 `%n`를 만나는 것은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  `%n`가 지원되는 경우\([\_set\_printf\_count\_output](../../c-runtime-library/reference/set-printf-count-output.md)를 참조하세요\), `%n`은 [printf 형식 필드 문자](../../c-runtime-library/printf-type-field-characters.md)에 설명된 대로 작동합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_printf_count_output`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [\_set\_printf\_count\_output](../../c-runtime-library/reference/set-printf-count-output.md)의 예제를 참조하십시오.  
  
## NET Framework 사용  
 해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.