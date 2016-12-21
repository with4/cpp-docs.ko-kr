---
title: "_getcwd_dbg, _wgetcwd_dbg | Microsoft Docs"
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
  - "_wgetcwd_dbg"
  - "_getcwd_dbg"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getcwd_dbg"
  - "_wgetcwd_dbg"
  - "getcwd_dbg"
  - "wgetcwd_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getcwd_dbg 함수"
  - "_wgetcwd_dbg 함수"
  - "현재 작업 디렉터리"
  - "디렉터리[C++], 현재 작업"
  - "getcwd_dbg 함수"
  - "wgetcwd_dbg 함수"
  - "디렉터리 작업"
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getcwd_dbg, _wgetcwd_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md) 함수의 디버그 버전입니다\(디버그 중에만 사용 가능\).  
  
## 구문  
  
```  
char *_getcwd_dbg(     char *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wgetcwd_dbg(     wchar_t *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### 매개 변수  
 `buffer`  
 경로의 저장소 위치입니다.  
  
 `maxlen`  
 경로의 최대 길이\(문자 수\)로 `_getcwd_dbg`의 경우 `char`자, `_wgetcwd_dbg`의 경우 `wchar_t`자입니다.  
  
 `blockType`  
 요청된 메모리 블록 형식으로 `_CLIENT_BLOCK` 또는 `_NORMAL_BLOCK`입니다.  
  
 `filename`  
 할당 작업 또는 `NULL`을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 할당 작업이 요청되었거나 `NULL`인 소스 파일의 줄 번호입니다.  
  
## 반환 값  
 `buffer`에 대한 포인터를 반환합니다.  `NULL` 반환 값은 오류를 나타내고 `errno`는 `ENOMEM`으로 설정되어 `maxlen`바이트를 할당할 메모리가 부족함을 나타내거나\(`NULL` 인수가 `buffer`로 지정된 경우\) `ERANGE`로 설정되어 경로가 `maxlen`자보다 긺을 나타냅니다.  
  
 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `NULL`이 첫 번째 매개 변수로 전달된 경우 \_`DEBUG`가 정의되면 이러한 함수가 `malloc` 및 `_malloc_dbg`의 디버그 버전을 사용하여 메모리를 할당한다는 점을 제외하면 `_getcwd_dbg` 및 `_wgetcwd_dbg` 함수는 `_getcwd` 및 `_wgetcwd`와 동일합니다.  자세한 내용은 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)을 참조하십시오.  
  
 대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다.  대신 `_CRTDBG_MAP_ALLOC` 플래그를 정의할 수 있습니다.  `_CRTDBG_MAP_ALLOC`를 정의하면 `_getcwd`및 `_wgetcwd`에 대한 호출이 각각 `_getcwd_dbg` 및 `_wgetcwd_dbg`로 다시 매핑되고 `blockType`은 `_NORMAL_BLOCK`으로 설정됩니다.  따라서 힙 블록을 `_CLIENT_BLOCK`으로 표시하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다.  자세한 내용은 [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하십시오.  
  
## 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tgetcwd_dbg`|`_getcwd_dbg`|`_getcwd_dbg`|`_wgetcwd_dbg`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_getcwd_dbg`|\<crtdbg.h\>|  
|`_wgetcwd_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 <xref:System.Environment.CurrentDirectory%2A>  
  
## 참고 항목  
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)