---
title: wcstombs, _wcstombs_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcstombs
- _wcstombs_l
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcstombs
- _wcstombs_l
dev_langs: C++
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ee05d4e8c8b36d92794293679992cb2c5ad5c36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wcstombs-wcstombsl"></a>wcstombs, _wcstombs_l
와이드 문자의 시퀀스를 멀티바이트 문자의 해당 시퀀스로 변환합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [wcstombs_s, _wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
size_t wcstombs(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count   
);  
size_t _wcstombs_l(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t wcstombs(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _wcstombs_l(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mbstr`  
 멀티바이트 문자 시퀀스의 주소입니다.  
  
 `wcstr`  
 와이드 문자 시퀀스의 주소입니다.  
  
 `count`  
 멀티바이트 출력 문자열에 저장할 수 있는 최대 바이트 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `wcstombs`는 멀티바이트 문자열을 올바르게 변환하는 경우 종결 `NULL`(있는 경우)을 제외하고 멀티바이트 출력 문자열에 기록된 바이트 수를 반환합니다. `mbstr` 인수가 `NULL`이면 `wcstombs`는 대상 문자열에 필요한 바이트 크기를 반환합니다. 경우 `wcstombs` 멀티 바이트 문자 변환 될 수 없는 와이드 문자를 만나면 형식으로 캐스팅 하는-1이 반환 `size_t` 설정 `errno` 를 `EILSEQ`합니다.  
  
## <a name="remarks"></a>설명  
 `wcstombs` 함수는 `wcstr`이 가리키는 와이드 문자열을 해당하는 멀티바이트 문자로 변환하고 결과를 `mbstr` 배열에 저장합니다. `count` 매개 변수는 멀티바이트 출력 문자열에 저장할 수 있는 최대 바이트 수(`mbstr`의 크기)를 나타냅니다. 일반적으로는 와이드 문자열을 변환할 때 필요한 바이트의 수를 알 수 없습니다. 출력 문자열에서 1바이트만 사용하면 되면 되는 와이드 문자도 있고 2바이트를 사용해야 하는 문자도 있습니다. 입력 문자열의 모든 와이드 문자(`NULL` 와이드 문자 포함)에 대해 멀티바이트 출력 문자열에 2바이트가 있으면 변환 성공이 보장됩니다.  
  
 `wcstombs`는 `count`가 나올 때나 그 전에 와이드 문자 null 문자(L'\0')를 발견하면 해당 문자를 8비트 0으로 변환한 후 실행을 중지합니다. 따라서 `mbstr`의 멀티바이트 문자열은 `wcstombs`가 변환 중에 와이드 문자 null 문자를 발견하는 경우에만 null로 종결됩니다. `wcstr`이 가리키는 시퀀스와 `mbstr`이 가리키는 시퀀스가 겹치는 경우 `wcstombs`의 동작이 정의되지 않습니다.  
  
 `mbstr` 인수가 `NULL`이면 `wcstombs`는 대상 문자열에 필요한 바이트 크기를 반환합니다.  
  
 `wcstombs`는 매개 변수의 유효성을 검사합니다. 경우 `wcstr` 은 `NULL`, if 또는 `count` 보다 크면 `INT_MAX`의 설명 대로 잘못 된 매개 변수 처리기를 호출 하는이 함수 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 합니다. 계속해서 실행하도록 허용된 경우 함수가 `errno`를 `EINVAL`로 설정하고 -1을 반환합니다.  
  
 `wcstombs`는 로캘 종속 동작을 수행해야 하는 경우 현재 로캘을 사용합니다. `_wcstombs_l`도 이와 동일하지만 전달된 로캘을 사용합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
 C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`wcstombs`|\<stdlib.h>|  
|`_wcstombs_l`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 이 프로그램은 `wcstombs` 함수의 동작을 보여 줍니다.  
  
```  
// crt_wcstombs.c  
// compile with: /W3  
// This example demonstrates the use  
// of wcstombs, which converts a string  
// of wide characters to a string of   
// multibyte characters.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t  count;  
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t *pWCBuffer = L"Hello, world.";  
  
    printf("Convert wide-character string:\n" );  
  
    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s instead  
    printf("   Characters converted: %u\n",  
            count );  
    printf("    Multibyte character: %s\n\n",  
           pMBBuffer );  
  
    free(pMBBuffer);  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 13  
    Multibyte character: Hello, world.  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)