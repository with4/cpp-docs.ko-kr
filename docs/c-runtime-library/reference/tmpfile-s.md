---
title: tmpfile_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e66ffa5fdbb1785191865eba92c9d673fb847ada
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="tmpfiles"></a>tmpfile_s
임시 파일을 만듭니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [tmpfile](../../c-runtime-library/reference/tmpfile.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t tmpfile_s(  
   FILE** pFilePtr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pFilePtr`  
 생성된 스트림에 대한 포인터의 주소를 저장할 포인터의 주소입니다.  
  
## <a name="return-value"></a>반환 값  
 정상적으로 실행되는 경우 0을 반환하고 오류 시에는 오류 코드를 반환합니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`pFilePtr`|**반환 값**|**f**`pFilePtr`의 내용|  
|----------------|----------------------|---------------------------------|  
|`NULL`|`EINVAL`|변경되지 않음|  
  
 위의 매개 변수 유효성 검사 오류가 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno`는 `EINVAL`로 설정되며 반환 값은 `EINVAL`입니다.  
  
## <a name="remarks"></a>설명  
 `tmpfile_s` 함수는 임시 파일을 만들고 해당 스트림에 대한 포인터를 `pFilePtr` 인수에 추가합니다. 임시 파일은 루트 디렉터리에 만들어집니다. 루트가 아닌 디렉터리에 임시 파일을 만들려면 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)과 함께 [tmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md) 또는 [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)을 사용합니다.  
  
 파일을 열 수 없는 경우 `tmpfile_s`는 `pFilePtr` 매개 변수에 `NULL`을 씁니다. 현재 작업 디렉터리가 변경되지 않았다고 가정할 때 이 임시 파일은 닫거나, 프로그램이 정상적으로 종료되거나, `_rmtmp`가 호출되면 자동으로 삭제됩니다. 임시 파일은 `w+b`(이진 읽기/쓰기) 모드로 열립니다.  
  
 `tmpfile_s.`을 사용하여 `TMP_MAX_S`(STDIO.H 참조)를 초과하는 호출을 시도하면 오류가 발생할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`tmpfile_s`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
> [!NOTE]
>  이 예제를 Windows Vista에서 실행하려면 관리 권한이 필요합니다.  
  
```  
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
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)
