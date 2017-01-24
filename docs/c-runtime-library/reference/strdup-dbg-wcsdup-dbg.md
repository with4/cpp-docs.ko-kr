---
title: "_strdup_dbg, _wcsdup_dbg | Microsoft Docs"
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
  - "_strdup_dbg"
  - "_wcsdup_dbg"
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
apitype: "DLLExport"
f1_keywords: 
  - "_wcsdup_dbg"
  - "strdup_dbg"
  - "_strdup_dbg"
  - "wcsdup_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strdup_dbg 함수"
  - "_wcsdup_dbg 함수"
  - "문자열 복사"
  - "문자열 중복"
  - "stdup_dbg 함수"
  - "문자열[C++], 복사"
  - "문자열[C++], 중복"
  - "wcsdup_dbg 함수"
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strdup_dbg, _wcsdup_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`malloc`의 디버그 버전을 사용하는 [\_strdup 및 \_wcsdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)의 버전입니다.  
  
## 구문  
  
```  
char *_strdup_dbg(    const char *strSource,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wcsdup_dbg(    const wchar_t *strSource,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### 매개 변수  
 `strSource`  
 Null 종료 소스 문자열입니다.  
  
 `blockType`  
 요청된 메모리 블록 형식으로 `_CLIENT_BLOCK` 또는 `_NORMAL_BLOCK`입니다.  
  
 `filename`  
 할당 작업 또는 NULL을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 할당 작업이 요청되었거나 NULL인 소스 파일의 줄 번호입니다.  
  
## 반환 값  
 이러한 각 함수는 복사한 문자열의 저장 위치에 대한 포인터를 반환하고 저장소를 할당할 수 없는 경우에는 `NULL`을 반환합니다.  
  
## 설명  
 `_DEBUG`가 정의되면 이러한 함수가 `malloc`, `_malloc_dbg`의 디버그 버전을 사용하여 중복 문자열에 필요한 메모리를 할당한다는 점을 제외하면 `_strdup_dbg` 및 `_wcsdup_dbg` 함수는 `_strdup` 및 `_wcsdup`와 동일합니다.  `_malloc_dbg`의 디버깅 기능에 대한 자세한 내용은 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)를 참조하세요.  
  
 대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다.  대신 `_CRTDBG_MAP_ALLOC` 플래그를 정의할 수 있습니다.  `_CRTDBG_MAP_ALLOC`을 정의하면 `_strdup` 및 `_wcsdup`에 대한 호출이 각각 `_strdup_dbg` 및 `_wcsdup_dbg`로 다시 매핑되고 `blockType`은 `_NORMAL_BLOCK`으로 설정됩니다.  따라서 힙 블록을 `_CLIENT_BLOCK`으로 표시하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다.  블록 형식에 대한 자세한 내용은 [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsdup_dbg`|`_strdup_dbg`|`_mbsdup`|`_wcsdup_dbg`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strdup_dbg`, `_wcsdup_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 디버그 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 [System::String::Clone](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strdup, \_wcsdup, \_mbsdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)   
 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)