---
title: "_get_wpgmptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_wpgmptr"
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
  - "get_wpgmptr"
  - "_get_wpgmptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_wpgmptr 함수"
  - "_wpgmptr 전역 변수"
  - "get_wpgmptr 함수"
  - "wpgmptr 전역 변수"
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _get_wpgmptr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`_wpgmptr` 전역 변수의 현재 값을 가져옵니다.  
  
## 구문  
  
```  
errno_t _get_wpgmptr(     wchar_t **pValue  );  
```  
  
#### 매개 변수  
 \[out\] `pValue`  
 `_wpgmptr` 변수의 현재 값으로 채울 문자열에 대한 포인터입니다.  
  
## 반환 값  
 성공하는 경우 0을 반환하고, 실패하는 경우 오류 코드를 반환합니다.  `pValue`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
## 설명  
 `_wpgmptr` 전역 변수는 프로세스와 연결된 실행 파일의 전체 경로를 와이드 문자열로 포함합니다.  자세한 내용은 [\_pgmptr, \_wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_wpgmptr`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [\_get\_pgmptr](../../c-runtime-library/reference/get-pgmptr.md)