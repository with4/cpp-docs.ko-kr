---
title: "_mbsnbcpy_s, _mbsnbcpy_s_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbcpy_s_l
- _mbsnbcpy_s
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
- mbsnbcpy_s_l
- _mbsnbcpy_s
- mbsnbcpy_s
- _mbsnbcpy_s_l
dev_langs: C++
helpviewer_keywords:
- _mbsnbcpy_s function
- tcsncpy_s function
- mbsnbcpy_s_l function
- _tcsncpy_s_l function
- mbsnbcpy_s function
- tcsncpy_s_l function
- _mbsnbcpy_s_l function
- _tcsncpy_s function
ms.assetid: dfff64ab-fe6f-49c4-99ba-75014e2b0cd6
caps.latest.revision: "29"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07fe25beabd14ab767c517a8f32786be3e6c53e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mbsnbcpys-mbsnbcpysl"></a>_mbsnbcpy_s, _mbsnbcpy_s_l
`n`바이트의 문자열을 대상 문자열에 복사합니다. 이러한 버전의 [_mbsnbcpy, _mbsnbcpy_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _mbsnbcpy_s(  
   unsigned char * strDest,  
   size_t sizeInBytes,  
   const unsigned char * strSource,  
   size_t count   
);  
errno_t _mbsnbcpy_s_l(  
   unsigned char * strDest,  
   size_t sizeInBytes,  
   const unsigned char * strSource,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _mbsnbcpy_s(  
   unsigned char (&strDest)[size],  
   const unsigned char * strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsnbcpy_s_l(  
   unsigned char (&strDest)[size],  
   const unsigned char * strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `strDest`  
 복사할 문자열의 대상입니다.  
  
 `sizeInBytes`  
 대상 버퍼 크기입니다.  
  
 `strSource`  
 복사할 문자열입니다.  
  
 `count`  
 복사할 바이트 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 성공한 경우에는 0이고, 잘못된 매개 변수가 전달된 경우에는 `EINVAL`입니다.  
  
## <a name="remarks"></a>설명  
 `_mbsnbcpy_s` 함수는 `strSource`에서 `strDest`로 `count`바이트를 복사합니다. `count`가 `strDest`의 크기를 초과하거나, 입력 문자열 중 하나가 null 포인터이거나, `sizeInBytes` 또는 `count`가 0이면 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 함수는 `EINVAL`을 반환합니다. 소스 문자열과 대상 문자열이 겹치는 경우 `_mbsnbcpy_s`의 동작이 정의되지 않습니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
> [!NOTE]
>  이 함수의 안전하지 않은 버전과 달리 `_mbsnbcpy_s`는 null 채우기를 수행하지 않으며 항상 null 종료 문자열입니다.  
  
 C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsncpy_s`|`_strncpy_s`|`_mbsnbcpy_s`|`_wcsncpy_s`|  
|`_tcsncpy_s_l`|`_strncpy_s_l`|`_mbsnbcpy_s_l`|`_wcsncpy_s_l`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_mbsnbcpy_s`|\<mbstring.h>|  
|`_mbsnbcpy_s_l`|\<mbstring.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](../../c-runtime-library/reference/strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)   
 [_mbsnbicmp, _mbsnbicmp_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [_mbsnbset, _mbsnbset_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)