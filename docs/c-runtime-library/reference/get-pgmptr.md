---
title: "_get_pgmptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_pgmptr"
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
  - "get_pgmptr"
  - "_get_pgmptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_pgmptr 함수"
  - "_pgmptr 전역 변수"
  - "get_pgmptr 함수"
  - "pgmptr 전역 변수"
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _get_pgmptr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`_pgmptr`  전역 변수의 현재 값을 가져옵니다.  
  
## 구문  
  
```  
errno_t _get_pgmptr(   
   char **pValue   
);  
```  
  
#### 매개 변수  
 \[out\] `pValue`  
 `_pgmptr` 변수의 현재 값을 사용하여 채워진 문자열에 대한 포인터 입니다.  
  
## 반환 값  
 성공 시 0을 반환합니다. 실패 시 오류 코드를 반환합니다.  만일 `pValue` 가 `NULL` 인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 보여주는 것처럼 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 에 설정하고 `EINVAL`을 반환합니다.  
  
## 설명  
 `_pgmptr`  전역 변수는 프로세스에 연결 된 실행파일의 전체 경로를 포함합니다.  자세한 내용은 [\_pgmptr, \_wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_pgmptr`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## NET Framework 사용  
 해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [\_get\_wpgmptr](../../c-runtime-library/reference/get-wpgmptr.md)