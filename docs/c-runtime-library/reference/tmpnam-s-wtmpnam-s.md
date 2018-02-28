---
title: tmpnam_s, _wtmpnam_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- tmpnam_s
- _wtmpnam_s
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
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
dev_langs:
- C++
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 844da11b981b99d5fe69861c3198d0508857a1a5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s, _wtmpnam_s
임시 파일을 만드는 데 사용할 수 있는 이름을 생성합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [tmpnam 및 _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t tmpnam_s(  
   char * str,  
   size_t sizeInChars   
);  
errno_t _wtmpnam_s(  
   wchar_t *str,  
   size_t sizeInChars   
);  
template <size_t size>  
errno_t tmpnam_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wtmpnam_s(  
   wchar_t (&str)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `str`  
 생성된 이름이 저장되는 포인터입니다.  
  
 [in] `sizeInChars`  
 버퍼의 크기(문자)입니다.  
  
## <a name="return-value"></a>반환 값  
 이 두 함수는 정상적으로 실행되면 0을 반환하고 오류 시에는 오류 번호를 반환합니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**반환 값**|**f**`str`의 내용|  
|`NULL`|any|`EINVAL`|수정 안 됨|  
|`NULL` 아님(올바른 메모리를 가리킴)|너무 짧음|`ERANGE`|수정 안 됨|  
  
 `str`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 이러한 각 함수는 현재 없는 파일의 이름을 반환합니다. `tmpnam_s`는 현재 작업 디렉터리의 고유 이름을 반환합니다. \fname21과 같이 파일 이름 앞에 백슬래시가 붙고 경로 정보는 없는 경우 현재 작업 디렉터리에 대해 해당 이름이 유효함을 나타냅니다.  
  
 `tmpnam_s`의 경우에는 생성된 이 파일 이름을 `str`에 저장할 수 있습니다. `tmpnam_s`에서 반환하는 문자열의 최대 길이는 STDIO.H에 정의된 `L_tmpnam_s`입니다. `str`이 `NULL`이면 `tmpnam_s`는 결과를 내부 정적 버퍼에 유지합니다. 따라서 모든 후속 호출에서는 이 값을 제거합니다. `tmpnam_s`에서 생성하는 이름은 프로그램에서 생성한 파일 이름과 파일 확장명(`tmpnam_s`에 대한 첫 번째 호출 이후 붙는 base32 형식의 순차적 숫자)으로 구성됩니다. 예를 들어 STDIO.H의 `TMP_MAX_S`가 INT_MAX인 경우의 파일 이름은 .1-.1vvvvvu입니다.  
  
 `tmpnam_s`는 운영 체제에서 가져온 OEM 코드 페이지에 따라 멀티바이트 문자 시퀀스를 인식하여 멀티바이트 문자열 인수를 자동으로 적절히 처리합니다. `_wtmpnam_s`는 `tmpnam_s`의 와이드 문자 버전이고, `_wtmpnam_s`의 인수와 반환 값은 와이드 문자 문자열입니다. `_wtmpnam_s` 및 `tmpnam_s`는 동일하게 작동합니다. 단, `_wtmpnam_s`는 멀티바이트 문자열을 처리하지 않습니다.  
  
 C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`tmpnam_s`|\<stdio.h>|  
|`_wtmpnam_s`|\<stdio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```  
// crt_tmpnam_s.c  
// This program uses tmpnam_s to create a unique filename in the  
// current working directory.   
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char name1[L_tmpnam_s];  
   errno_t err;  
   int i;  
  
   for (i = 0; i < 15; i++)  
   {  
      err = tmpnam_s( name1, L_tmpnam_s );  
      if (err)  
      {  
         printf("Error occurred creating unique filename.\n");  
         exit(1);  
      }  
      else  
      {  
         printf( "%s is safe to use as a temporary file.\n", name1 );  
      }  
   }    
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)