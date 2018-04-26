---
title: tmpfile_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- tmpfile_s
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
- tmpfile_s
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57c230dedd3415a272e168b586a16ccb03f5d29a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="tmpfiles"></a>tmpfile_s

임시 파일을 만듭니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [tmpfile](tmpfile.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t tmpfile_s(
   FILE** pFilePtr
);
```

### <a name="parameters"></a>매개 변수

*pFilePtr*<br/>
생성된 스트림에 대한 포인터의 주소를 저장할 포인터의 주소입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0을 반환하고 오류 시에는 오류 코드를 반환합니다.

### <a name="error-conditions"></a>오류 조건

|*pFilePtr*|**반환 값**|**내용을***pFilePtr* |
|----------------|----------------------|---------------------------------|
|**NULL**|**EINVAL**|변경되지 않음|

위의 매개 변수 유효성 검사 오류가 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 값 반환 **EINVAL**합니다.

## <a name="remarks"></a>설명

**tmpfile_s** 함수 임시 파일을 만들고 대 한 포인터를 해당 스트림에 넣습니다는 *pFilePtr* 인수입니다. 임시 파일은 루트 디렉터리에 만들어집니다. 루트가 아닌 디렉터리에 임시 파일을 만들려면 [fopen](fopen-wfopen.md)과 함께 [tmpnam_s](tmpnam-s-wtmpnam-s.md) 또는 [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)을 사용합니다.

파일을 열 수 없는 경우 **tmpfile_s** 씁니다 **NULL** 에 *pFilePtr* 매개 변수입니다. 파일이 닫힌 경우 또는 일반적으로 프로그램을 종료 하면이 임시 파일은 삭제 자동으로 **_rmtmp** 를 호출 하는 현재 작업 디렉터리를 변경 하지 않습니다. 임시 파일을 열 **w + b** (이진 읽기/쓰기) 모드입니다.

시도 하면 오류가 발생할 수 있습니다 이상 **TMP_MAX_S** (STDIO 참조 합니다. H) 사용 하 여 호출 **tmpfile_s**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**tmpfile_s**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

> [!NOTE]
> 이 예제에서는 Windows에서 실행 하려면 관리자 권한이 필요할 수 있습니다.

```C
// crt_tmpfile_s.c
// This program uses tmpfile_s to create a
// temporary file, then deletes this file with _rmtmp.
//

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char tempstring[] = "String to be written";
   int  i;
   errno_t err;

   // Create temporary files.
   for( i = 1; i <= 3; i++ )
   {
      err = tmpfile_s(&stream);
      if( err )
         perror( "Could not open new temporary file\n" );
      else
         printf( "Temporary file %d was created\n", i );
   }

   // Remove temporary files.
   printf( "%d temporary files deleted\n", _rmtmp() );
}
```

```Output
Temporary file 1 was created
Temporary file 2 was created
Temporary file 3 was created
3 temporary files deleted
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_rmtmp](rmtmp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
