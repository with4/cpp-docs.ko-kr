---
title: "_tempnam_dbg, _wtempnam_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtempnam_dbg"
  - "_tempnam_dbg"
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
  - "wtempnam_dbg"
  - "tempnam_dbg"
  - "_tempnam_dbg"
  - "_wtempnam_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tempnam_dbg 함수"
  - "_wtempnam_dbg 함수"
  - "파일 이름[C++], 임시 파일 만들기"
  - "파일 이름[C++], 임시"
  - "tempnam_dbg 함수"
  - "임시 파일, 만들기"
  - "wtempnam_dbg 함수"
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _tempnam_dbg, _wtempnam_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`malloc, _malloc_dbg`의 디버그 버전을 사용하는 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)의 함수 버전입니다.  
  
## 구문  
  
```  
char *_tempnam_dbg(    const char *dir,    const char *prefix,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wtempnam_dbg(    const wchar_t *dir,    const wchar_t *prefix,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### 매개 변수  
 `dir`  
 TMP 환경 함수가 없는 경우 또는 TMP가 올바른 디렉터리가 아닌 경우 파일 이름에 사용되는 경로입니다.  
  
 `prefix`  
 `_tempnam`에서 반환하는 이름 앞에 추가되는 문자열입니다.  
  
 `blockType`  
 요청된 메모리 블록 형식으로 `_CLIENT_BLOCK` 또는 `_NORMAL_BLOCK`입니다.  
  
 `filename`  
 할당 작업 또는 `NULL`을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 할당 작업이 요청되었거나 `NULL`인 소스 파일의 줄 번호입니다.  
  
## 반환 값  
 실패하면 각 함수는 생성된 이름에 대한 포인터 또는 `NULL`을 반환합니다.  TMP 환경 변수 및 `dir` 매개 변수에 잘못된 디렉터리 이름이 지정되어 있으면 실패할 수 있습니다.  
  
> [!NOTE]
>  `free`\(또는 `free_dbg`\)는 `_tempnam_dbg` 및 `_wtempnam_dbg`가 할당한 포인터에 대해 호출할 필요가 없습니다.  
  
## 설명  
 `NULL`이 첫 번째 매개 변수로 전달된 경우 `_DEBUG`가 정의되면 이러한 함수가 `malloc` 및 `_malloc_dbg`의 디버그 버전을 사용하여 메모리를 할당한다는 점을 제외하면 `_tempnam_dbg`및 `_wtempnam_dbg` 함수는 `_tempnam`및 `_wtempnam`함수와 동일합니다.  자세한 내용은 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)을 참조하십시오.  
  
 대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다.  대신 `_CRTDBG_MAP_ALLOC` 플래그를 정의할 수 있습니다.  `_CRTDBG_MAP_ALLOC`을 정의하면 `_tempnam` 및 `_wtempnam`에 대한 호출이 각각  `_tempnam_dbg` 및 `_wtempnam_dbg`로 다시 매핑되고 `blockType`은 `_NORMAL_BLOCK`으로 설정됩니다.  따라서 힙 블록을 `_CLIENT_BLOCK`으로 표시하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다.  자세한 내용은 [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)