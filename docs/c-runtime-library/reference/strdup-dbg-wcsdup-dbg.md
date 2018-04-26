---
title: _strdup_dbg, _wcsdup_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _strdup_dbg
- _wcsdup_dbg
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
- _wcsdup_dbg
- strdup_dbg
- _strdup_dbg
- wcsdup_dbg
dev_langs:
- C++
helpviewer_keywords:
- _wcsdup_dbg function
- stdup_dbg function
- copying strings
- duplicating strings
- strings [C++], copying
- strings [C++], duplicating
- _strdup_dbg function
- wcsdup_dbg function
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aaea554a4663ff0f4a8853b2ad3ed147af99668b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="strdupdbg-wcsdupdbg"></a>_strdup_dbg, _wcsdup_dbg

버전의 [_strdup 및 _wcsdup](strdup-wcsdup-mbsdup.md) 의 디버그 버전을 사용 하는 **malloc**합니다.

## <a name="syntax"></a>구문

```C
char *_strdup_dbg(
   const char *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wcsdup_dbg(
   const wchar_t *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*strSource*<br/>
Null 종료 소스 문자열입니다.

*blockType*<br/>
요청 된 메모리 블록의 형식: **_CLIENT_BLOCK** 또는 **_NORMAL_BLOCK**합니다.

*filename*<br/>
할당 작업 또는 NULL을 요청한 소스 파일의 이름에 대한 포인터입니다.

*linenumber*<br/>
할당 작업이 요청되었거나 NULL인 소스 파일의 줄 번호입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수는 복사한 문자열에 대 한 저장소 위치에 대 한 포인터를 반환 하거나 **NULL** 저장소를 할당할 수 없는 경우.

## <a name="remarks"></a>설명

**_strdup_dbg** 및 **_wcsdup_dbg** 함수는 동일 **_strdup** 및 **_wcsdup** 점을 제외 하 고, **_ 디버그** 는 디버그 버전의를 사용 하 여 이러한 함수를 정의 **malloc**, **_malloc_dbg**, 중복된 문자열에 대 한 메모리를 할당할 수 있습니다. 디버깅 기능에 대 한 내용은 **_malloc_dbg**, 참조 [_malloc_dbg](malloc-dbg.md)합니다.

대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다. 플래그를 정의할 수 대신 **_CRTDBG_MAP_ALLOC**합니다. 때 **_CRTDBG_MAP_ALLOC** 정의에 대 한 호출이 **_strdup** 및 **_wcsdup** 다시 매핑됩니다 **_strdup_dbg** 및 **_ wcsdup_dbg**각각와 *blockType* 로 설정 **_NORMAL_BLOCK**합니다. 따라서 힙 블록으로 표시 하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 하지 **_CLIENT_BLOCK**합니다. 블록 형식에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup_dbg**|**_strdup_dbg**|**_mbsdup**|**_wcsdup_dbg**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_strdup_dbg**, **_wcsdup_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 디버그 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdup, _wcsdup, _mbsdup](strdup-wcsdup-mbsdup.md)<br/>
[힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
