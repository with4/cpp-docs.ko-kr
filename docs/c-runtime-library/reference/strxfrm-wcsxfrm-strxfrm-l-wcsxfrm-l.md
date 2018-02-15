---
title: strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strxfrm
- _tcsxfrm
- wcsxfrm
dev_langs:
- C++
helpviewer_keywords:
- strxfrm_l function
- _tcsxfrm function
- _strxfrm_l function
- strxfrm function
- wcsxfrm_l function
- wcsxfrm function
- string comparison [C++], transforming strings
- tcsxfrm function
- strings [C++], comparing locale
- _wcsxfrm_l function
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0545fd71f571caa2fbb12cefb010c274cbda9f28
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="strxfrm-wcsxfrm-strxfrml-wcsxfrml"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
로캘별 정보를 기반으로 문자열을 변형합니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_t strxfrm(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
size_t wcsxfrm(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
size_t _strxfrm_l(  
   char *strDest,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
size_t wcsxfrm_l(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `strDest`  
 대상 문자열입니다.  
  
 `strSource`  
 소스 문자열입니다.  
  
 `count`  
 에 문자 수가 최대 `strDest`합니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 종료 null 문자를 세지 않고 변형된 문자열의 길이를 반환합니다. 반환 값이 `count`보다 크거나 같으면 `strDest`의 콘텐츠는 예측할 수 없습니다. 오류에서 각 함수는 `errno`를 설정하고 `INT_MAX`를 반환합니다. 잘못된 문자의 경우 `errno`는 `EILSEQ`로 설정됩니다.  
  
## <a name="remarks"></a>설명  
 `strxfrm` 함수는 `strSource`가 가리키는 문자열을 `strDest`에 저장된 새 데이터 정렬된 형식으로 변환합니다. null 문자를 포함하여 `count`개 이하의 문자가 변환되어 결과 문자열에 저장됩니다. 로캘의 `LC_COLLATE` 범주 설정을 사용하여 변환이 일어납니다. `LC_COLLATE`에 대한 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `strxfrm`은 로캘 종속인 동작에 현재 로캘을 사용합니다. 현재 로캘 대신 전달된 로캘을 사용한다는 것을 제외하면 `_strxfrm_l`도 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
 변환 이후 변형된 문자열 두 개를 사용하여 `strcmp`를 호출할 경우 두 원본 문자열에 적용된 `strcoll`의 호출과 동일한 결과가 발생합니다. `strcoll` 및 `stricoll`과 마찬가지로, `strxfrm`은 자동으로 멀티바이트 문자열을 적절하게 처리합니다.  
  
 `wcsxfrm`은 `strxfrm`의 와이드 문자 버전이며, `wcsxfrm`의 문자열 인수는 와이드 문자 포인터입니다. `wcsxfrm`의 경우 문자열 변환 이후 변형된 문자열 두 개를 사용하여 `wcscmp`를 호출할 경우 두 원본 문자열에 적용된 `wcscoll`의 호출과 동일한 결과가 발생합니다. 그렇지 않으면 `wcsxfrm`과 `strxfrm`이 동일하게 작동합니다. `wcsxfrm`은 로캘 종속적인 동작에 현재 로캘을 사용합니다. `_wcsxfrm_l`은 현재 로캘 대신에 전달된 로캘을 사용합니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. `strSource`가 null 포인터이거나, `strDest`가 NULL 포인터이거나(count가 0이 아닌 경우), `count`가 `INT_MAX`보다 큰 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 `errno`를 `EINVAL`로 설정하고 `INT_MAX`을 반환합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsxfrm`|`strxfrm`|`strxfrm`|`wcsxfrm`|  
|`_tcsxfrm_l`|`_strxfrm_l`|`_strxfrm_l`|`_wcsxfrm_l`|  
  
 "C" 로캘에서 문자 집합(ASCII 문자 집합)의 순서는 사전적 문자 순서와 같습니다. 그러나 다른 로캘에서 문자 집합의 문자 순서는 사전적 문자 순서와 다를 수 있습니다. 예를 들어 특정 유럽 로캘의 문자 집합에서 문자 'a'(값 0x61)는 문자 '&\#x00E4;'(값 0xE4) 앞에 오지만 사전적으로는 문자 'ä'가 'a' 앞에 옵니다.  
  
 문자 집합과 사전적 문자 순서가 다른 로캘에서는 원본 문자열에 대해 `strxfrm`을 사용한 다음 결과 문자열에 `strcmp`를 사용하여 현재 로캘의 `LC_COLLATE` 범주 설정에 따라 사전적 문자열 비교를 수행하십시오. 따라서 위의 로캘에서 사전순으로 두 문자열을 비교하기 위해서는 `strxfrm`을 원본 문자열에, `strcmp`를 결과 문자열에 사용합니다. 또는 원본 문자열에 `strcoll` 대신 `strcmp`을 사용할 수 있습니다.  
  
 `strxfrm`은 기본적으로 `LCMAP_SORTKEY`를 사용하는 [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) 래퍼입니다.  
  
 다음 식의 값은 원본 문자열의 `strxfrm` 변환을 저장하기 위해 필요한 배열의 크기입니다.  
  
```  
1 + strxfrm( NULL, string, 0 )  
```  
  
 "C" 로캘의 경우 `strxfrm`은 다음과 같습니다.  
  
```  
strncpy( _string1, _string2, _count );  
return( strlen( _string1 ) );  
```  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`strxfrm`|\<string.h>|  
|`wcsxfrm`|\<string.h> 또는 \<wchar.h>|  
|`_strxfrm_l`|\<string.h>|  
|`_wcsxfrm_l`|\<string.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)