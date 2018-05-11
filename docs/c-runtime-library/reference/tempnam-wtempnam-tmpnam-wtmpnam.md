---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
- wtempnam
- _wtmpnam
- wtmpnam
- tmpnam
- _wtempnam
- _tempnam
dev_langs:
- C++
helpviewer_keywords:
- wtempnam function
- file names [C++], creating temporary
- _tempnam function
- ttmpnam function
- tmpnam function
- tempnam function
- wtmpnam function
- temporary files, creating
- file names [C++], temporary
- _ttmpnam function
- _wtmpnam function
- _wtempnam function
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55ff069d72d68493eee524ea2f9c012d2fc7f534
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="tempnam-wtempnam-tmpnam-wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam

임시 파일을 만드는 데 사용할 수 있는 이름을 생성합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [tmpnam_s, _wtmpnam_s](tmpnam-s-wtmpnam-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_tempnam(
   const char *dir,
   const char *prefix
);
wchar_t *_wtempnam(
   const wchar_t *dir,
   const wchar_t *prefix
);
char *tmpnam(
   char *str
);
wchar_t *_wtmpnam(
   wchar_t *str
);
```

### <a name="parameters"></a>매개 변수

*prefix*<br/>
앞에서 반환 된 이름에 추가 될 문자열 **_tempnam**합니다.

*dir*<br/>
TMP 환경 함수가 없는 경우 또는 TMP가 올바른 디렉터리가 아닌 경우 파일 이름에 사용되는 경로입니다.

*str*<br/>
생성된 이름이 저장되며 함수가 반환하는 이름과 동일하게 지정되는 포인터입니다. 이 매개 변수를 사용하면 생성되는 이름을 편리하게 저장할 수 있습니다.

## <a name="return-value"></a>반환 값

생성 된 이름에 대 한 포인터를 반환 이러한 각 함수 또는 **NULL** 오류가 발생 하는 경우. 시도 하면 오류가 발생할 수 있습니다 이상 **TMP_MAX** (STDIO 참조 합니다. H) 사용 하 여 호출 **tmpnam** 사용 하는 경우 또는 **_tempnam** 및 TMP 환경 변수에 지정 된 잘못 된 디렉터리 이름이 고는 *dir* 매개 변수입니다.

> [!NOTE]
> 반환 된 포인터 **tmpnam** 및 **_wtmpnam** 내부 정적 버퍼를 가리킵니다. 이러한 포인터를 할당 해제하기 위해 [free](free.md)를 호출해서는 안 됩니다. **무료** 포인터에 의해 할당에 대 한 호출 해야 **_tempnam** 및 **_wtempnam**합니다.

## <a name="remarks"></a>설명

이러한 각 함수는 현재 없는 파일의 이름을 반환합니다. **tmpnam** 현재 작업 디렉터리에 고유한 이름을 반환 하 고 **_tempnam** 현재 이외의 디렉터리에 고유 이름을 생성할 수 있습니다. \fname21과 같이 파일 이름 앞에 백슬래시가 붙고 경로 정보는 없는 경우 현재 작업 디렉터리에 대해 해당 이름이 유효함을 나타냅니다.

에 대 한 **tmpnam**,이 생성 된 파일 이름에 저장할 수 있습니다 *str*합니다. 경우 *str* 은 **NULL**, 다음 **tmpnam** 내부 정적 버퍼에는 결과 남겨 둡니다. 따라서 모든 후속 호출에서는 이 값을 제거합니다. 에 의해 생성 된 이름 **tmpnam** 구성 프로그램에서 생성 된 파일 이름의 하 고, 첫 번째 호출 후 **tmpnam**, 기본 32에서 연속 된 숫자의 파일 확장명 (경우에 순서 대로.1-.vvu **TMP_MAX**  STDIO에 있습니다. H는 32, 767).

**_tempnam** 다음 규칙에 따라 선택한 디렉터리에 대 한 고유한 파일 이름이 생성 됩니다.

- TMP 환경 변수가 정의되어 있으며 올바른 디렉터리 이름으로 설정되어 있으면 TMP가 지정한 디렉터리에 대해 고유한 파일 이름이 생성됩니다.

- 존재 하지 않는 디렉터리의 이름으로 설정 된 경우 또는 TMP 환경 변수가 정의 되지 않은 경우 **_tempnam** ´ ֲ는 *dir* 를 고유한 이름을 기반인 경로와 매개 변수입니다.

- TMP 환경 변수가 정의 되지 않은 경우 또는 존재 하지 않는 디렉터리의 이름으로 설정 되 고 *dir* 있거나 **NULL** 존재 하지 않는 디렉터리의 이름으로 설정 또는 **_ tempnam** 고유 이름을 생성 하는 현재 작업 디렉터리를 사용 합니다. 현재 경우 두 TMP 및 *dir* 존재 하지 않는 디렉터리의 이름을 지정는 **_tempnam** 함수 호출이 실패 합니다.

반환 하는 이름은 **_tempnam** 의 연결한 것 *접두사* 및 지정된 된 디렉터리에 대 한 고유한 파일 이름을 만들기 위해 결합 합니다. 일련 번호를 합니다. **_tempnam** 확장명이 없는 파일 이름을 생성 합니다. **_tempnam** 사용 하 여 [malloc](malloc.md) filename;에 대 한 공간을 할당 하는 프로그램은 더 이상 필요 없는 경우이 공간을 확보 하는 일을 담당 합니다.

**_tempnam** 및 **tmpnam** 멀티 바이트 문자열 인수를 적절 하 게 핸들의 OEM 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 하며 운영 체제에서 자동으로 부여 합니다. **_wtempnam** 의 와이드 문자 버전이 **_tempnam**; 인수 및 반환 값이 **_wtempnam** 는 와이드 문자 문자열입니다. **_wtempnam** 및 **_tempnam** 점을 제외 하 고 동일 하 게 작동 **_wtempnam** 멀티 바이트 문자열을 처리 하지 않습니다. **_wtmpnam** 의 와이드 문자 버전이 **tmpnam**; 인수 및 반환 값의 **_wtmpnam** 는 와이드 문자 문자열입니다. **_wtmpnam** 및 **tmpnam** 점을 제외 하 고 동일 하 게 작동 **_wtmpnam** 멀티 바이트 문자열을 처리 하지 않습니다.

경우 **_DEBUG** 및 **_CRTDBG_MAP_ALLOC** 정의 된 **_tempnam** 및 **_wtempnam** 호출에 의해 교체 [_tempnam _dbg 및 _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md)합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam**|**tmpnam**|**tmpnam**|**_wtmpnam**|
|**_ttempnam**|**_tempnam**|**_tempnam**|**_wtempnam**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_tempnam**|\<stdio.h>|
|**_wtempnam**, **_wtmpnam**|\<stdio.h> 또는 \<wchar.h>|
|**tmpnam**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_tempnam.c
// compile with: /W3
// This program uses tmpnam to create a unique filename in the
// current working directory, then uses _tempnam to create
// a unique filename with a prefix of stq.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char* name1 = NULL;
   char* name2 = NULL;

   // Create a temporary filename for the current working directory:
   if( ( name1 = tmpnam( NULL ) ) != NULL ) // C4996
   // Note: tmpnam is deprecated; consider using tmpnam_s instead
      printf( "%s is safe to use as a temporary file.\n", name1 );
   else
      printf( "Cannot create a unique filename\n" );

   // Create a temporary filename in temporary directory with the
   // prefix "stq". The actual destination directory may vary
   // depending on the state of the TMP environment variable and
   // the global variable P_tmpdir.

   if( ( name2 = _tempnam( "c:\\tmp", "stq" ) ) != NULL )
      printf( "%s is safe to use as a temporary file.\n", name2 );
   else
      printf( "Cannot create a unique filename\n" );

   // When name2 is no longer needed :
   if(name2)
     free(name2);

}
```

```Output
\s1gk. is safe to use as a temporary file.
C:\DOCUME~1\user\LOCALS~1\Temp\2\stq2 is safe to use as a temporary file.
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile](tmpfile.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
