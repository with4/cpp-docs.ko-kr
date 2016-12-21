---
title: "_set_doserrno | Microsoft Docs"
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
  - "_set_doserrno"
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
  - "_set_doserrno"
  - "set_doserrno"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_doserrno 전역 변수"
  - "_set_doserrno 함수"
  - "doserrno 전역 변수"
  - "set_doserrno 함수"
ms.assetid: 8686c159-3797-4705-a53e-7457869ca6f3
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_doserrno
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 전역 변수 값을 설정하세요.  
  
## 구문  
  
```  
errno_t _set_doserrno(   
   int value   
);  
```  
  
#### 매개 변수  
 \[in\] `value`  
 `_doserrno`의 새 값입니다.  
  
## 반환 값  
 성공하면 0을 반환합니다.  
  
## 설명  
 가능 값은 Errno.h에서 정의됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_set_doserrno`|\<stdlib.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 참고 항목  
 [\_get\_doserrno](../../c-runtime-library/reference/get-doserrno.md)   
 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)