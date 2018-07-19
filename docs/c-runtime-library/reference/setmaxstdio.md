---
title: _setmaxstdio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _setmaxstdio
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
- setmaxstdio
- _setmaxstdio
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 785fcc05c6b19086c14edc85983749894c867c18
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407670"
---
# <a name="setmaxstdio"></a>_setmaxstdio

동시에 열리는 파일 수에 대 한 최대 설정한는 **stdio** 수준입니다.

## <a name="syntax"></a>구문

```C
int _setmaxstdio(
   int newmax
);
```

### <a name="parameters"></a>매개 변수

*newmax*<br/>
동시에 열리는 파일 수에 대 한 새 최대값은 **stdio** 수준입니다.

## <a name="return-value"></a>반환 값

반환 *newmax* 성공 하면 그렇지 않으면-1입니다.

경우 *newmax* 는 보다 작은 **_IOB_ENTRIES** 에 설명 된 대로 잘못 된 매개 변수 처리기 운영 체제에서 사용할 수 있는 핸들의 최대 수는 호출 다음에 큰 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수는-1 반환 하 고 집합을 계속 하려면 실행 허용 된 경우 **errno** 를 **EINVAL**합니다.

이 오류 및 다른 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**_setmaxstdio** 에서 동시에 열려 있는 파일 수에 대 한 최대 값을 변경 하는 함수는 **stdio** 수준입니다.

C 런타임 I/O는 이제 이전 버전에 비해 Win32 플랫폼에서 훨씬 더 많은 파일을 열 수 있도록 지원합니다. 최대 2, 048 파일에 동시에 열 수는 [lowio 수준](../../c-runtime-library/low-level-i-o.md) (즉, 열리고 통해는 **열기 (_o)**, **읽기 (_r)**, **_write**, I/O 함수 패밀리 등). 최대 512 파일에 동시에 열 수는 [stdio 수준](../../c-runtime-library/stream-i-o.md) (즉, 열리고 통해는 **fopen**, **fgetc**, **fputc** 을 함수 패밀리 등). 열려 있는 파일에 512의 한계는 **stdio** 최대 2, 048 방법으로 수준을 올릴 수는 **_setmaxstdio** 함수입니다.

때문에 **stdio**-와 같은 함수 수준 **fopen**, 맨 위에 빌드됩니다는 **lowio** 함수, 2, 048의 최대는 하드 상한값이 수에 대 한 동시에 C 런타임 라이브러리를 통해 액세스 되는 파일을 엽니다.

> [!NOTE]
> 이 상한은 특정 Win32 플랫폼 및 구성에서 지원하는 수를 초과할 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

참조 [_getmaxstdio](getmaxstdio.md) 사용 하는 예제에 대 한 **_setmaxstdio**합니다.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
