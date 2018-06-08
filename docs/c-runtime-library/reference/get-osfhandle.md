---
title: _get_osfhandle | Microsoft 문서
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_osfhandle
- _get_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15bddcf3d94935f56fa2e23b6ebd0398ed379c54
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569851"
---
# <a name="getosfhandle"></a>_get_osfhandle

지정된 파일 설명자와 연결된 운영 체제 파일 핸들을 검색합니다.

## <a name="syntax"></a>구문

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
기존 파일 설명자입니다.

## <a name="return-value"></a>반환 값

경우에 운영 체제 파일 핸들 반환 *fd* 유효 합니다. 그렇지 않으면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 허용 된 경우이 함수는 반환 **INVALID_HANDLE_VALUE** (-1)을 설정 하 고 **errno** 를 **EBADF**, 잘못 된 파일 핸들을 나타내는입니다. 컴파일러 경고를 Win32 파일 핸들을 예상 하는 루틴에서 결과 사용 하는 경우를 방지 하려면 캐스팅 하는 **처리** 유형입니다.

## <a name="remarks"></a>설명

운영 체제 (OS) 파일 핸들이 여 가져온 파일을 닫으려면 **_get_osfhandle**, 호출 [_close](close.md) 파일 설명자에 *fd*합니다. 호출 하지 마십시오 **CloseHandle** 이 함수의 반환 값에 있습니다. 기본 OS 파일 핸들은에서 소유는 *fd* 파일 설명자, 및가 닫혀 [_close](close.md) 호출 된다고 *fd*합니다. 파일 설명자가 소유 하는 경우는 **파일 \***  다음 호출 하는 스트림 [fclose](fclose-fcloseall.md) 그에 **파일 \***  스트림을 닫고 파일 설명자 및 기본 OS 파일 핸들입니다. 이 경우 호출 하지 않으면 [_close](close.md) 파일 설명자에 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
