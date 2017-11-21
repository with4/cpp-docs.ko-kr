---
title: _strdec, _wcsdec, _mbsdec, _mbsdec_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcsdec
- _strdec
- _mbsdec
- _mbsdec_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strdec
- mbsdec_l
- strdec
- _mbsdec
- _mbsdec_l
- mbsdec
- wcsdec
- _wcsdec
dev_langs: C++
helpviewer_keywords:
- mbsdec_l function
- mbsdec function
- tcsdec function
- _tcsdec function
- _strdec function
- _wcsdec function
- _mbsdec_l function
- strdec function
- wcsdec function
- _mbsdec function
ms.assetid: ae37c223-800f-48a9-ae8e-38c8d20af2dd
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4df8de18c2256b4e9034b4b0c80f7c4edf85fe91
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="strdec-wcsdec-mbsdec-mbsdecl"></a>_strdec, _wcsdec, _mbsdec, _mbsdec_l
문자열 포인터를 한 문자 뒤로 이동합니다.  
  
> [!IMPORTANT]
>  Windows 런타임에서 실행되는 응용 프로그램에서는 `mbsdec` 및 `mbsdec_l`을 사용할 수는 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned char *_strdec(  
   const unsigned char *start,  
   const unsigned char *current   
);  
unsigned wchar_t *_wcsdec(  
   const unsigned wchar_t *start,  
   const unsigned wchar_t *current   
);  
unsigned char *_mbsdec(  
   const unsigned char *start,  
   const unsigned char *current   
);  
unsigned char *_mbsdec_l(  
   const unsigned char *start,  
   const unsigned char *current,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `start`  
 모든 문자에 대 한 포인터 (또는 `_mbsdec` 및 `_mbsdec_l`, 모든 멀티 바이트 문자의 첫 번째 바이트) 소스 문자열;의 `start` 앞에 야 `current` 소스 문자열의 합니다.  
  
 `current`  
 모든 문자에 대 한 포인터 (또는 `_mbsdec` 및 `_mbsdec_l`, 모든 멀티 바이트 문자의 첫 번째 바이트) 소스 문자열;의 `current` 따라야 `start` 소스 문자열의 합니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `_mbsdec``_mbsdec_l`, `_strdec`, 및 `_wcsdec` 바로 앞에 있는 문자에 대 한 포인터를 반환할 각 `current`; `_mbsdec` 반환 `NULL` 경우의 값 `start` 보다 크거나 같은 `current`합니다. `_tcsdec`는 이러한 함수 중 하나에 매핑되며 해당 반환 값은 매핑에 따라 달라집니다.  
  
## <a name="remarks"></a>설명  
 `_mbsdec` 및 `_mbsdec_l` 함수는 `start`가 포함된 문자열에서 `current` 바로 앞에 있는 멀티바이트 문자의 첫 번째 바이트에 대한 포인터를 반환합니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요.  `_mbsdec`는 현재 사용 중인 로캘에 따라 멀티바이트 문자 시퀀스를 인식하고 `_mbsdec_l`은 전달된 로캘 매개 변수를 대신 사용한다는 점을 제외하고는 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `start` 또는 `current`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이 함수는 `EINVAL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
> [!IMPORTANT]
>  이러한 함수는 버퍼 오버런 위협에 노출될 수 있습니다. 버퍼 오버런은 불필요한 권한 상승을 발생시킬 수 있으므로 시스템 공격에 사용될 수 있습니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsdec`|`_strdec`|`_mbsdec`|`_wcsdec`|  
  
 `_strdec` 및 `_wcsdec`는 `_mbsdec` 및 `_mbsdec_l`의 싱글바이트 문자 및 와이드 문자 버전입니다. `_strdec` 및 `_wcsdec`는 이러한 매핑을 위해서만 제공되고 그 외에는 사용하면 안 됩니다.  
  
 자세한 내용은 [일반 텍스트 매핑 사용](../../c-runtime-library/using-generic-text-mappings.md) 및 [일반 텍스트 매핑](../../c-runtime-library/generic-text-mappings.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_mbsdec`|\<mbstring.h>|\<mbctype.h>|  
|`_mbsdec_l`|\<mbstring.h>|\<mbctype.h>|  
|`_strdec`|\<tchar.h>||  
|`_wcsdec`|\<tchar.h>||  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예에서는 `_tcsdec`의 사용법을 보여줍니다.  
  
```  
  
      #include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main()  
{  
   const TCHAR *str = _T("12345");  
   cout << "str: " << str << endl;  
  
   const TCHAR *str2;  
   str2 = str + 2;  
   cout << "str2: " << str2 << endl;  
  
   TCHAR *answer;  
   answer = _tcsdec( str, str2 );  
   cout << "answer: " << answer << endl;  
  
   return (0);   
}  
  
```  
  
 다음 예에서는 `_mbsdec`의 사용법을 보여줍니다.  
  
```  
#include <iostream>  
#include <mbstring.h>  
using namespace std;  
  
int main()   
{   
   char *str = "12345";  
   cout << "str: " << str << endl;  
  
   char *str2;  
   str2 = str + 2;   
   cout << "str2: " << str2 << endl;  
  
   unsigned char *answer;  
   answer = _mbsdec( reinterpret_cast<unsigned char *>( str ), reinterpret_cast<unsigned char *>( str2 ));  
  
   cout << "answer: " << answer << endl;  
  
   return (0);   
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [_strinc, _wcsinc, _mbsinc, _mbsinc_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)   
 [_strninc, _wcsninc, _mbsninc, _mbsninc_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)