---
title: wctomb_s, _wctomb_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wctomb_s_l
- wctomb_s
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
- wctomb_s
- _wctomb_s_l
dev_langs:
- C++
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3025340d4af81f20fd086d07058ac820828dda75
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="wctombs-wctombsl"></a>wctomb_s, _wctomb_s_l
와이드 문자를 해당 멀티바이트 문자로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pRetValue`  
 결과를 나타내는 코드 또는 바이트 수입니다.  
  
 [out] `mbchar`  
 멀티바이트 문자의 주소입니다.  
  
 [in] `sizeInBytes`  
 `mbchar` 버퍼의 크기입니다.  
  
 [in] `wchar`  
 와이드 문자입니다.  
  
 [in] `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 성공시 0, 실패시 오류 코드.  
  
 오류 조건  
  
|`mbchar`|`sizeInBytes`|반환 값|`pRetValue`|  
|--------------|-------------------|------------------|-----------------|  
|`NULL`|>0|`EINVAL`|수정 안 됨|  
|any|>`INT_MAX`|`EINVAL`|수정 안 됨|  
|any|너무 작음|`EINVAL`|수정 안 됨|  
  
 위의 오류 조건 중 하나라도 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 `wctomb`는 `EINVAL`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `wctomb_s` 함수는 `wchar` 인수를 해당 멀티바이트 문자로 변환하고 결과를 `mbchar`에 저장합니다. 모든 프로그램에서 언제든지 이 함수를 호출할 수 있습니다.  
  
 `wctomb_s`는 와이드 문자를 멀티바이트 문자로 변환하는 경우 와이드 문자의 바이트 수(항상 `MB_CUR_MAX`보다 크지 않음)를 `pRetValue`가 가리키는 정수에 추가합니다. `wchar`이 와이드 문자 null 문자(L'\0')이면 `wctomb_s`는 `pRetValue`를 1로 채웁니다. 대상 포인터 `mbchar`이 NULL이면 `wctomb_s`는 `pRetValue`에 0을 추가합니다. 현재 로캘 변환이 가져올 수 없으면 `wctomb_s` 에-1을 넣습니다 `pRetValue`합니다.  
  
 `wctomb_s`는 로캘 종속 정보가 필요한 경우 현재 로캘을 사용합니다. `_wctomb_s_l`도 이와 동일하지만 전달된 로캘을 사용합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`wctomb_s`|\<stdlib.h>|  
|`_wctomb_s_l`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 이 프로그램은 `wctomb` 함수의 동작을 보여 줍니다.  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
```Output  
Convert a wide character:  
   Characters converted: 1  
   Multibyte character: a  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)