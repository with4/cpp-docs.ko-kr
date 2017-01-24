---
title: "_get_errno | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_errno"
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
  - "_get_errno"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_get_errno 함수"
  - "errno 전역 변수"
  - "get_errno 함수"
ms.assetid: b3fd5ebc-f41b-4314-a2f4-2f2d79d6e740
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_errno
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

errno 전역 변수의 현재 값을 가져옵니다.  
  
## 구문  
  
```  
errno_t _get_errno(   
   int * pValue   
);  
```  
  
#### 매개 변수  
 \[out\] `pValue`  
 `errno` 변수의 현재 값으로 채워진 정수를 가리키는 포인터입니다.  
  
## 반환 값  
 성공 시 0을 반환합니다. 실패 시 오류 코드를 반환합니다.  `pValue`가 `NULL`이면, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 에 설정하고 `EINVAL`을 반환합니다.  
  
## 설명  
 `errno`에서 가능한 값은 Errno.h에서 정의됩니다.  [errno 상수](../../c-runtime-library/errno-constants.md)도 참조하십시오.  
  
## 예제  
  
```  
// crt_get_errno.c  
#include <stdio.h>  
#include <fcntl.h>  
#include <sys/stat.h>  
#include <share.h>  
#include <errno.h>  
  
int main()  
{  
   errno_t err;  
   int pfh;  
   _sopen_s( &pfh, "nonexistent.file", _O_WRONLY, _SH_DENYNO, _S_IWRITE );  
   _get_errno( &err );  
   printf( "errno = %d\n", err );  
   printf( "fyi, ENOENT = %d\n", ENOENT );  
}  
```  
  
  **errnos \= 2**  
**fyi, ENOENT \= 2**   
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_get_errno`|\<stdlib.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## NET Framework 사용  
 해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [\_set\_errno](../../c-runtime-library/reference/set-errno.md)   
 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)