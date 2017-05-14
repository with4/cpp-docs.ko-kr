---
title: "_ltoa_s, _ltow_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ltoa_s
- _ltow_s
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
apitype: DLLExport
f1_keywords:
- _ltow_s
- _ltoa_s
- ltoa_s
- ltow_s
dev_langs:
- C++
helpviewer_keywords:
- converting integers
- _ltoa_s function
- ltow_s function
- long integer conversion to string
- converting numbers, to strings
- ltoa_s function
- _ltow_s function
ms.assetid: d7dc61ea-1ccd-412d-b262-555a58647386
caps.latest.revision: 18
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
ms.openlocfilehash: 098bb1dcf673931ab4c0d3682fafcc442835d76f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="ltoas-ltows"></a>_ltoa_s, _ltow_s
long 정수를 문자열로 변환합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_ltoa, _ltow](../../c-runtime-library/reference/ltoa-ltow.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _ltoa_s(  
    long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ltow_s(  
    long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ltoa_s(  
    long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ltow_s(  
    long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value`  
 변환할 숫자입니다.  
  
 `str`  
 결과 문자열에 대한 버퍼입니다.  
  
 `sizeOfstr`  
 `_ltoa_s`의 경우 `str`의 크기(바이트) 또는 `_ltow_s`의 경우 단어의 크기입니다.  
  
 `radix`  
 `value`의 기본입니다.  
  
## <a name="return-value"></a>반환 값  
 함수가 정상적으로 실행되는 경우 0이고 그렇지 않으면 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 `_ltoa_s` 함수는 `value`의 숫자를 null로 끝나는 문자열로 변환하고 결과(최대 33바이트)를 `str`에 저장합니다. `radix` 인수 기본을 지정 `value`, 2-36 범위에 이어야 합니다. 경우 `radix` 이 10 및 `value` 가 음수인 경우 저장된 된 문자열의 첫 번째 문자는 음수 기호 (-). `_ltow_s`는 `_ltoa_s`의 와이드 문자 버전입니다. `_ltow_s`의 두 번째 인수는 와이드 문자열입니다.  
  
 `str`이 `NULL` 포인터이거나 `sizeOfstr`이 0보다 작거나 같은 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 -1을 반환하고 `errno`를 `EINVAL`로 설정하거나, `value` 또는 `str`이 long 정수의 범위를 벗어나면 -1을 반환하고 `errno`를 `ERANGE`로 설정합니다.  
  
 C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot_s`|`_ltoa_s`|`_ltoa_s`|`_ltow_s`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_ltoa_s`|\<stdlib.h>|  
|`_ltow_s`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [_ultoa_s, _ultow_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md)
