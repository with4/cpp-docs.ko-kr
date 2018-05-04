---
title: _CrtSetDumpClient | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d5fecc90b4b7259f1440a0a0d86277c769c4e16
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient

덤프 하는 응용 프로그램 정의 함수를 설치 **_CLIENT_BLOCK** 메모리 블록 (디버그 버전에만 해당)을 입력 합니다.

## <a name="syntax"></a>구문

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>매개 변수

*dumpClient*<br/>
C 런타임 디버그 메모리 덤프 프로세스에 연결할 새로운 클라이언트 정의 메모리 덤프 함수입니다.

## <a name="return-value"></a>반환 값

이전에 정의된 클라이언트 블록 덤프 함수를 반환합니다.

## <a name="remarks"></a>설명

**_CrtSetDumpClient** 자체 함수에 저장 된 덤프 개체를 연결 하는 응용 프로그램 기능을 사용 하면 **_CLIENT_BLOCK** 메모리 블록에 C 런타임 메모리 덤프 프로세스를 디버깅 합니다. 결과적으로, 될 때마다 디버그 덤프 함수 같은 [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) 또는 [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) 덤프는 **_CLIENT_BLOCK** 메모리 블록, 응용 프로그램의 덤프 함수도 호출 됩니다. **_CrtSetDumpClient** 쉬운 방법으로 메모리 누수를 탐지 하 고 유효성 검사 또는에 저장 된 데이터의 내용을 보고에 대 한 응용 프로그램을 제공 **_CLIENT_BLOCK** 블록입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은에 대 한 호출이 **_CrtSetDumpClient** 전처리 중 제거 됩니다.

**_CrtSetDumpClient** 함수에 지정 된 새 응용 프로그램 정의 덤프 함수를 설치 *dumpClient* 이전에 정의 된 덤프 함수를 반환 합니다. 클라이언트 블록 덤프 함수의 예제는 다음과 같습니다.

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

*userPortion* 인수는 메모리 블록의 사용자 데이터 부분의 시작 부분에 대 한 포인터 및 *blockSize* 할당된 된 메모리의 크기 (바이트)에서 블록을 지정 합니다. 클라이언트 블록 덤프 함수는 반환 해야 **void**합니다. 에 전달 되는 클라이언트 덤프 함수에 대 한 포인터 **_CrtSetDumpClient** 유형의 **_CRT_DUMP_CLIENT**Crtdbg.h에 정의 된 대로:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

작동 하는 함수에 대 한 자세한 내용은 **_CLIENT_BLOCK** 메모리 블록 형식, 참조 [클라이언트 블록 후크 함수](/visualstudio/debugger/client-block-hook-functions)합니다. [_CrtReportBlockType](crtreportblocktype.md) 함수는 블록 형식과 하위 형식에 대한 정보를 반환하는 데 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>
