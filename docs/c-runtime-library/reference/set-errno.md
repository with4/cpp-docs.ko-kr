---
title: "_set_errno | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_errno"
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
  - "set_errno"
  - "_set_errno"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_errno 함수"
  - "errno 전역 변수"
  - "set_errno 함수"
ms.assetid: d338914a-1894-4cf3-ae45-f2c4eb26590b
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _set_errno
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`errno` 전역 변수의 값을 설정합니다.  
  
## 구문  
  
```  
errno_t _set_errno(   
   int value   
);  
```  
  
#### 매개 변수  
 \[in\] `value`  
 `errno`의 새 값입니다.  
  
## 반환 값  
 성공하면 0을 반환합니다.  
  
## 설명  
 가능 값은 Errno.h에서 정의됩니다.  [errno 상수](../../c-runtime-library/errno-constants.md)도 참조하십시오.  
  
## 예제  
  
```  
// crt_set_errno.c  
#include <stdio.h>  
#include <errno.h>  
  
int main()  
{  
   _set_errno( EILSEQ );  
   perror( "Oops" );  
}  
```  
  
  **경고: 잘못된 바이트 시퀀스**   
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_set_errno`|\<stdlib.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 참고 항목  
 [\_get\_errno](../../c-runtime-library/reference/get-errno.md)   
 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)