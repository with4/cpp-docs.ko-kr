---
title: wctomb, _wctomb_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wctomb_l
- wctomb
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
- wctomb
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 3d199cba90dd2440a7a467c95d32e2a5a75f8cbf
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="wctomb-wctombl"></a>wctomb, _wctomb_l
와이드 문자를 해당 멀티바이트 문자로 변환합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int wctomb(  
   char *mbchar,  
   wchar_t wchar   
);  
int _wctomb_l(  
   char *mbchar,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mbchar`  
 멀티바이트 문자의 주소입니다.  
  
 `wchar`  
 와이드 문자입니다.  
  
## <a name="return-value"></a>반환 값  
 `wctomb`는 와이드 문자를 멀티바이트 문자로 변환하는 경우 와이드 문자의 바이트 수(항상 `MB_CUR_MAX`보다 크지 않음)를 반환합니다. `wchar`이 와이드 문자 null 문자(L'\0')이면 `wctomb`는 1을 반환합니다. 대상 포인터 `mbchar`이 NULL이면 `wctomb`는 0을 반환합니다. 현재 로캘 변환이 가져올 수 없으면 `wctomb` -1을 반환 하 고 `errno` 로 설정 된 `EILSEQ`합니다.  
  
## <a name="remarks"></a>설명  
 `wctomb` 함수는 `wchar` 인수를 해당 멀티바이트 문자로 변환하고 결과를 `mbchar`에 저장합니다. 모든 프로그램에서 언제든지 이 함수를 호출할 수 있습니다. `wctomb`는 로캘 종속 동작에 대해 현재 로캘을 사용합니다. `_wctomb_l`은 대신 전달된 로캘을 사용하는 것을 제외하고는 `wctomb`와 같습니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `wctomb`는 매개 변수의 유효성을 검사합니다. `mbchar`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 -1을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`wctomb`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 이 프로그램은 wctomb 함수의 동작을 보여 줍니다.  
  
```  
// crt_wctomb.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int i;  
   wchar_t wc = L'a';  
   char *pmb = (char *)malloc( MB_CUR_MAX );  
  
   printf( "Convert a wide character:\n" );  
   i = wctomb( pmb, wc ); // C4996  
   // Note: wctomb is deprecated; consider using wctomb_s  
   printf( "   Characters converted: %u\n", i );  
   printf( "   Multibyte character: %.1s\n\n", pmb );  
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
