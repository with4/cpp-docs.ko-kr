---
title: "_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_invalid_parameter_handler"
  - "_get_thread_local_invalid_parameter_handler"
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
  - "_get_invalid_parameter_handler"
  - "stdlib/_get_invalid_parameter_handler"
  - "_get_thread_local_invalid_parameter_handler"
  - "stdlib/_get_thread_local_invalid_parameter_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_thread_local_invalid_parameter_handler 함수"
  - "_get_invalid_parameter_handler 함수"
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# _get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CRT가 잘못 된 인수를 발견할 때 호출 되는 함수를 가져옵니다.  
  
## 구문  
  
```  
_invalid_parameter_handler _get_invalid_parameter_handler(void);  
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);  
```  
  
## 반환 값  
 현재 설정에 대 한 포인터를 설정 하지 않은 경우 null 포인터 또는 잘못 된 매개 변수 처리기 함수입니다.  
  
## 설명  
 `_get_invalid_parameter_handler` 함수는 현재 설정 가져옵니다 글로벌 잘못 된 매개 변수 처리기입니다. 전역 잘못 된 매개 변수 처리기가 설정 되 면 null 포인터를 반환 합니다. 마찬가지로,는 `_get_thread_local_invalid_parameter_handler` 처리기가 설정 되 면 호출 되는 스레드 또는 null 포인터의 현재 스레드 로컬 잘못 된 매개 변수 처리기를 가져옵니다. 전역 커서와 스레드 로컬 잘못 된 매개 변수 처리기를 설정 하는 방법에 대 한 정보를 참조 하십시오. [\_set\_invalid\_parameter\_handler, \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)합니다.  
  
 반환 된 잘못 된 매개 변수 처리기 함수 포인터는 다음 유형:  
  
```c  
typedef void (__cdecl* _invalid_parameter_handler)(  
    wchar_t const*,  
    wchar_t const*,  
    wchar_t const*,   
    unsigned int,  
    uintptr_t  
    );  
```  
  
 잘못 된 매개 변수 처리기에 대 한 자세한 내용은 참조의 프로토타입을 [\_set\_invalid\_parameter\_handler, \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_invalid_parameter_handler`, `_get_thread_local_invalid_parameter_handler`|C: \< stdlib.h \><br /><br /> C \+ \+: \< d l i b \> 또는 \< stdlib.h \>|  
  
 `_get_invalid_parameter_handler` 및 `_get_thread_local_invalid_parameter_handler` 함수는 Microsoft 전용입니다. 호환성 정보를 참조 하십시오. [호환성](../../c-runtime-library/compatibility.md)합니다.  
  
## 참고 항목  
 [\_set\_invalid\_parameter\_handler, \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)   
 [보안이 강화된 CRT 함수 버전](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)