---
title: _tempnam_dbg, _wtempnam_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wtempnam_dbg
- _tempnam_dbg
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
dev_langs:
- C++
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4f407dce7825a593273206ada02680d6da99e9a0
ms.lasthandoff: 02/24/2017

---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg, _wtempnam_dbg
디버그 버전의 `malloc, _malloc_dbg`를 사용하는 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)의 함수 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
char *_tempnam_dbg(  
   const char *dir,  
   const char *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wtempnam_dbg(  
   const wchar_t *dir,  
   const wchar_t *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dir`  
 TMP 환경 함수가 없는 경우 또는 TMP가 올바른 디렉터리가 아닌 경우 파일 이름에 사용되는 경로입니다.  
  
 `prefix`  
 `_tempnam`에서 반환하는 이름 앞에 추가되는 문자열입니다.  
  
 `blockType`  
 메모리 블록의 요청된 형식(`_CLIENT_BLOCK` 또는 `_NORMAL_BLOCK`)입니다.  
  
 `filename`  
 할당 작업 또는 `NULL`을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 할당 작업이 요청되었거나 `NULL`인 소스 파일의 줄 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 실패하면 각 함수는 생성된 이름에 대한 포인터 또는 `NULL`을 반환합니다. TMP 환경 변수 및 `dir` 매개 변수에 잘못된 디렉터리 이름이 지정되어 있으면 실패할 수 있습니다.  
  
> [!NOTE]
>  `free`(또는 `free_dbg`)는 `_tempnam_dbg` 및 `_wtempnam_dbg`가 할당한 포인터에 대해 호출할 필요가 없습니다.  
  
## <a name="remarks"></a>설명  
 `_tempnam_dbg` 및 `_wtempnam_dbg` 함수는 `_tempnam` 및 `_wtempnam`과 동일합니다. 단, `NULL`이 첫 번째 매개 변수로 전달된 경우 _`_DEBUG`가 정의되어 있으면 이러한 함수는 `malloc` 및 `_malloc_dbg`의 디버그 버전을 사용합니다. 자세한 내용은 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)를 참조하세요.  
  
 대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다. 대신 `_CRTDBG_MAP_ALLOC` 플래그를 정의할 수 있습니다. `_CRTDBG_MAP_ALLOC`을 정의하면 `_tempnam` 및 `_wtempnam`에 대한 호출이 각각 `_tempnam_dbg` 및 `_wtempnam_dbg`로 다시 매핑되고 `blockType`은 `_NORMAL_BLOCK`으로 설정됩니다. 따라서 힙 블록을 `_CLIENT_BLOCK`으로 표시하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다. 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
