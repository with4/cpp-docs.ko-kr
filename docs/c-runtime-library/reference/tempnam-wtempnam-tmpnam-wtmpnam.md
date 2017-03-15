---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 20
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
ms.openlocfilehash: e4f0eff8758694e97bfb310f9cfa650cb28cefa4
ms.lasthandoff: 02/24/2017

---
# <a name="tempnam-wtempnam-tmpnam-wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam
임시 파일을 만드는 데 사용할 수 있는 이름을 생성합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [tmpnam_s, _wtmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
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
  
#### <a name="parameters"></a>매개 변수  
 `prefix`  
 `_tempnam`에서 반환하는 이름 앞에 추가되는 문자열입니다.  
  
 `dir`  
 TMP 환경 함수가 없는 경우 또는 TMP가 올바른 디렉터리가 아닌 경우 파일 이름에 사용되는 경로입니다.  
  
 `str`  
 생성된 이름이 저장되며 함수가 반환하는 이름과 동일하게 지정되는 포인터입니다. 이 매개 변수를 사용하면 생성되는 이름을 편리하게 저장할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 이러한 각 함수는 생성된 이름에 대한 포인터를 반환하거나, 오류가 발생하면 `NULL`을 반환합니다. `tmpnam`을 사용하여 `TMP_MAX`(STDIO.H 참조)보다 많은 호출을 시도하거나, `_tempnam`를 사용할 때 TMP 환경 변수와 `dir` 매개 변수에 잘못된 디렉터리 이름이 지정되어 있으면 오류가 발생할 수 있습니다.  
  
> [!NOTE]
>  `tmpnam` 및 `_wtmpnam`에서 반환하는 포인터는 내부 정적 버퍼를 가리킵니다. 이러한 포인터를 할당 해제하기 위해 [free](../../c-runtime-library/reference/free.md)를 호출해서는 안 됩니다. `free`는 `_tempnam` 및 `_wtempnam`에서 할당한 포인터에 대해 호출해야 합니다.  
  
## <a name="remarks"></a>설명  
 이러한 각 함수는 현재 없는 파일의 이름을 반환합니다. `tmpnam`은 현재 작업 디렉터리에서 고유한 이름을 반환하며, `_tempnam`을 사용하면 현재 디렉터리가 아닌 디렉터리에서 고유한 이름을 생성할 수 있습니다. \fname21과 같이 파일 이름 앞에 백슬래시가 붙고 경로 정보는 없는 경우 현재 작업 디렉터리에 대해 해당 이름이 유효함을 나타냅니다.  
  
 `tmpnam`의 경우에는 생성된 이 파일 이름을 `str`에 저장할 수 있습니다. `str`이 `NULL`이면 `tmpnam`은 결과를 내부 정적 버퍼에 유지합니다. 따라서 모든 후속 호출에서는 이 값을 제거합니다. `tmpnam`에서 생성하는 이름은 프로그램에서 생성한 파일 이름과 파일 확장명(`tmpnam`에 대한 첫 번째 호출 이후 붙는 base32 형식의 순차적 숫자)으로 구성됩니다. 예를 들어 STDIO.H의 `TMP_MAX`가 32,767인 경우의 파일 이름은 .1-.vvu입니다.  
  
 `_tempnam`은 다음 규칙에 따라 선택한 디렉터리에 대해 고유한 파일 이름을 생성합니다.  
  
-   TMP 환경 변수가 정의되어 있으며 올바른 디렉터리 이름으로 설정되어 있으면 TMP가 지정한 디렉터리에 대해 고유한 파일 이름이 생성됩니다.  
  
-   TMP 환경 변수가 정의되어 있지 않거나 없는 디렉터리의 이름으로 설정되어 있으면 `_tempnam`은 고유한 이름을 생성할 경로로 `dir` 매개 변수를 사용합니다.  
  
-   TMP 환경 변수가 정의되어 있지 않거나 없는 디렉터리 이름으로 설정되어 있고 `dir`이 `NULL`이거나 없는 디렉터리 이름으로 설정되어 있으면 `_tempnam`은 현재 작업 디렉터리를 사용하여 고유한 이름을 생성합니다. 현재는 TMP와 `dir`이 둘 다 없는 디렉터리의 이름을 지정하는 경우 `_tempnam` 함수 호출은 실패합니다.  
  
 `_tempnam`에서 반환하는 이름은 `prefix`과 순차 번호가 연결된 형태입니다. 이 번호는 지정된 디렉터리에 대해 고유한 파일 이름을 만들기 위해 결합됩니다. `_tempnam`은 확장명이 없는 파일 이름을 생성합니다. `_tempnam`은 [malloc](../../c-runtime-library/reference/malloc.md)를 사용하여 파일 이름을 위한 공간을 할당합니다. 프로그램은 이 공간이 더 이상 필요하지 않으면 해제합니다.  
  
 `_tempnam` 및 `tmpnam`은 운영 체제에서 가져온 OEM 코드 페이지에 따라 멀티바이트 문자 시퀀스를 인식하여 멀티바이트 문자열 인수를 자동으로 적절히 처리합니다. `_wtempnam`은 `_tempnam`의 와이드 문자 버전이고, `_wtempnam`의 인수와 반환 값은 와이드 문자열입니다. `_wtempnam` 및 `_tempnam`은 동일하게 작동합니다. 단, `_wtempnam`은 멀티바이트 문자열을 처리하지 않습니다. `_wtmpnam`는 `tmpnam`의 와이드 문자 버전이고, `_wtmpnam`의 인수와 반환 값은 와이드 문자 문자열입니다. `_wtmpnam` 및 `tmpnam`은 동일하게 작동합니다. 단, `_wtmpnam`은 멀티바이트 문자열을 처리하지 않습니다.  
  
 `_DEBUG` 및 `_CRTDBG_MAP_ALLOC`를 정의하는 경우 `_tempnam` 및 `_wtempnam`은 [_tempnam_dbg 및 _wtempnam_dbg](../../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md) 호출로 바뀝니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam`|`tmpnam`|`tmpnam`|`_wtmpnam`|  
|`_ttempnam`|`_tempnam`|`_tempnam`|`_wtempnam`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_tempnam`|\<stdio.h>|  
|`_wtempnam`, `_wtmpnam`|\<stdio.h> 또는 \<wchar.h>|  
|`tmpnam`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
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
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)
