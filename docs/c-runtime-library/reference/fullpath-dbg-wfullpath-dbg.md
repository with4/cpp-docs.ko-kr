---
title: _fullpath_dbg, _wfullpath_dbg | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wfullpath_dbg
- _fullpath_dbg
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
- wfullpath_dbg
- _wfullpath_dbg
- _fullpath_dbg
- fullpath_dbg
dev_langs:
- C++
helpviewer_keywords:
- _fullpath_dbg function
- relative file paths
- absolute paths
- fullpath_dbg function
- _wfullpath_dbg function
- wfullpath_dbg function
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c7ff7b300473389281a7386d49843987456f116
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="fullpathdbg-wfullpathdbg"></a>_fullpath_dbg, _wfullpath_dbg

버전의 [_fullpath, _wfullpath](fullpath-wfullpath.md) 의 디버그 버전을 사용 하는 **malloc** 메모리를 할당 합니다.

## <a name="syntax"></a>구문

```C
char *_fullpath_dbg(
   char *absPath,
   const char *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wfullpath_dbg(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*absPath*<br/>
절대 또는 전체 경로 이름을 포함 하는 버퍼에 대 한 포인터 또는 **NULL**합니다.

*relPath*<br/>
상대 경로 이름입니다.

*MaxLength*<br/>
절대 경로 이름 버퍼의 최대 길이 (*absPath*). 이 길이 바이트 단위에 대 한 **_fullpath** 는 와이드 문자 (**wchar_t**)에 대 한 **_wfullpath**합니다.

*blockType*<br/>
요청 된 메모리 블록의 형식: **_CLIENT_BLOCK** 또는 **_NORMAL_BLOCK**합니다.

*filename*<br/>
할당 작업을 요청한 소스 파일의 이름에 대 한 포인터 또는 **NULL**합니다.

*linenumber*<br/>
할당 작업이 요청 된 소스 파일의 줄 번호 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

각 함수는 절대 경로 이름을 포함 하는 버퍼에 대 한 포인터를 반환 합니다 (*absPath*). 오류가 발생 하는 경우 (값에 전달 하는 경우에 예를 들어 *relPath* 유효 하지 않거나 찾을 수 없는 드라이브 문자가 포함 된 경우 또는 작성된 된 절대 경로 이름 길이 (*absPath*) 보다 크면 *maxLength*) 함수가 반환 **NULL**합니다.

## <a name="remarks"></a>설명

**_fullpath_dbg** 및 **_wfullpath_dbg** 함수는 동일 **_fullpath** 및 **_wfullpath** 점을 제외 하 고, **_DEBUG** 은 디버그 버전의를 사용 하 여 이러한 함수 정의 **malloc**, **_malloc_dbg**, NULL은 첫 번째 매개 변수로 전달 되 면 메모리를 할당할 수 있습니다. 디버깅 기능에 대 한 내용은 **_malloc_dbg**, 참조 [_malloc_dbg](malloc-dbg.md)합니다.

대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다. 대신, 정의할 수 있습니다는 **_CRTDBG_MAP_ALLOC** 플래그입니다. 때 **_CRTDBG_MAP_ALLOC** 정의에 대 한 호출이 **_fullpath** 및 **_wfullpath** 다시 매핑됩니다 **_fullpath_dbg** 및 **_wfullpath_dbg**각각와 *blockType* 로 설정 **_NORMAL_BLOCK**합니다. 따라서 힙 블록으로 표시 하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 하지 **_CLIENT_BLOCK**합니다. 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_fullpath_dbg**|\<crtdbg.h>|
|**_wfullpath_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
