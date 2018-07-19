---
title: _isatty | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _isatty
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
- _isatty
dev_langs:
- C++
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4be35fce0a790751683a4bf8a0cceaf938fea82
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402461"
---
# <a name="isatty"></a>_isatty

파일 설명자가 문자 장치와 연결되어 있는지 여부를 확인합니다.

## <a name="syntax"></a>구문

```C
int _isatty( int fd );
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
테스트할 장치를 나타내는 파일 설명자입니다.

## <a name="return-value"></a>반환 값

**_isatty** 설명자가 문자 장치에 연결 하는 경우 0이 아닌 값을 반환 합니다. 그렇지 않으면 **_isatty** 0을 반환 합니다.

## <a name="remarks"></a>설명

**_isatty** 함수 확인 여부 *fd* (터미널, 콘솔, 프린터 또는 직렬 포트) 문자 장치와 연결 합니다.

이 함수 유효성을 검사는 *fd* 매개 변수입니다. 경우 *fd* 는 잘못 된 파일 포인터에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수는 0 반환 하 고 집합을 계속 하려면 실행 허용 된 경우 **errno** 를 **EBADF**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_isatty**|\<io.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_isatty.c
/* This program checks to see whether
* stdout has been redirected to a file.
*/

#include <stdio.h>
#include <io.h>

int main( void )
{
   if( _isatty( _fileno( stdout ) ) )
      printf( "stdout has not been redirected to a file\n" );
   else
      printf( "stdout has been redirected to a file\n");
}
```

### <a name="sample-output"></a>샘플 출력

```Output
stdout has not been redirected to a file
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
