---
title: "_mbccpy_s, _mbccpy_s_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbccpy_s
- _mbccpy_s_l
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
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
dev_langs:
- C++
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72b2e155dafe0b5fb5a83e5e62ea95fd2c3657e6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s, _mbccpy_s_l
한 문자열에서 다른 문자열로 멀티바이트 문자를 복사합니다. 이러한 버전의 [_mbccpy, _mbccpy_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 참조 [CRT 함수는 유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _mbccpy_s(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src   
);  
errno_t _mbccpy_s_l(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
);  
template <size_t size>  
errno_t _mbccpy_s(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src   
); // C++ only  
template <size_t size>  
errno_t _mbccpy_s_l(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `dest`  
 복사 대상입니다.  
  
 [in] `buffSizeInBytes`  
 대상 버퍼의 크기입니다.  
  
 [out] `pCopied`  
 복사된 바이트 수로 채워집니다(성공할 경우 1 또는 2). 개수가 중요하지 않은 경우 `NULL`을 전달합니다.  
  
 [in] `src`  
 복사할 멀티바이트 문자입니다.  
  
 [in] `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다. `src` 또는 `dest`가 `NULL`이거나 `buffSizeinBytes`바이트 이상이 `dest`에 복사되면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이 함수는 `EINVAL`를 반환하며 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `_mbccpy_s` 함수는 `src`에서 `dest`로 하나의 멀티바이트 문자를 복사합니다. `src`가 [_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md)의 암시적 호출에 의해 결정된 멀티바이트 문자의 선행 바이트를 가리키지 않는 경우 `src`가 가리키는 싱글바이트가 복사됩니다. `src`가 선행 바이트를 가리키지만 다음 바이트가 0이어서 유효하지 않으면 0이 `dest`에 복사되고 `errno`는 `EILSEQ`로 설정되며 함수는 `EILSEQ`를 반환합니다.  
  
 `_mbccpy_s`는 null 종결자를 추가하지 않습니다. 그러나 `src`가 null 문자를 가리키면 해당 null 문자가 `dest`에 복사됩니다. 이는 단순히 일반 싱글바이트 복사본입니다.  
  
 `pCopied`의 값은 복사된 바이트 수로 채워집니다. 연산이 성공할 경우 가능한 값은 1과 2입니다. `NULL`이 전달되면 이 매개 변수는 무시됩니다.  
  
|`src`|`dest`에 복사됨|`pCopied`|반환 값|  
|-----------|----------------------|---------------|------------------|  
|비선행 바이트|비선행 바이트|1|0|  
|0|0|1|0|  
|선행 바이트와 그 뒤의 0이 아닌 값|선행 바이트와 그 뒤의 0이 아닌 값|2|0|  
|선행 바이트와 그 뒤의 0|0|1|`EILSEQ`|  
  
 두 번째 행은 첫 번째 행의 특수 사례일 뿐입니다. 또한 표에서는 `buffSizeInBytes`  >=  `pCopied`로 가정합니다.  
  
 `_mbccpy_s`는 로캘 종속 동작에 대해 현재 로캘을 사용합니다. `_mbccpy_s_l`은 `_mbccpy_s`와 동일합니다. 단, `_mbccpy_s_l`은 모든 로캘 종속 동작에 대해 전달된 로캘을 사용합니다.  
  
 C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tccpy_s`|매크로 또는 인라인 함수에 매핑됩니다.|`_mbccpy_s`|매크로 또는 인라인 함수에 매핑됩니다.|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_mbccpy_s`|\<mbstring.h>|  
|`_mbccpy_s_l`|\<mbstring.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)