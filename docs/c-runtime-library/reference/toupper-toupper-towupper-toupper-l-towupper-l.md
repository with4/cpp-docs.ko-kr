---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- towupper
- _toupper
- _totupper
- toupper
dev_langs:
- C++
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
caps.latest.revision: 16
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e782f6168d48ecc1d24b90f2030909de32c9ee26
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l
문자를 대문자로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int toupper(  
   int c   
);  
int _toupper(  
   int c   
);  
int towupper(  
   wint_t c   
);  
int _toupper_l(  
   int c ,  
   _locale_t locale  
);  
int _towupper_l(  
   wint_t c ,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 변환할 문자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 이러한 각 루틴은 가능한 경우 `c`의 복사본을 변환하고 결과를 반환합니다.  
  
 `c`가 와이드 문자인 경우(`iswlower`가 0이 아니며 `iswupper`가 0이 아닌 해당하는 와이드 문자가 있음) `towupper`는 해당하는 와이드 문자를 반환하고 그렇지 않으면 `towupper`는 변경되지 않은 `c`를 반환합니다.  
  
 오류를 나타내기 위해 예약된 반환 값은 없습니다.  
  
 `toupper`가 필요한 값을 제공하려면 [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) 및 [islower](../../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md)가 둘 다 0이 아닌 값을 반환해야 합니다.  
  
## <a name="remarks"></a>설명  
 이러한 각 루틴은 가능하며 적절한 경우 지정된 소문자를 대문자로 변환합니다. `towupper`의 대/소문자 변환은 로캘에 따라 다릅니다. 현재 로캘에서 유효한 문자의 대/소문자만 변경됩니다. `_l` 접미사가 없는 함수는 현재 설정된 로캘을 사용합니다. 이러한 함수의 `_l` 접미사가 있는 버전은 로캘을 매개 변수로 사용하며 현재 설정된 로캘 대신 해당 로캘을 사용합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `toupper`가 필요한 값을 제공하려면 [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) 및 [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md)가 둘 다 0이 아닌 값을 반환해야 합니다.  
  
 [데이터 변환 루틴](../../c-runtime-library/data-conversion.md)  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totupper`|`toupper`|`_mbctoupper`|`towupper`|  
|`_totupper_l`|`_toupper_l`|`_mbctoupper_l`|`_towupper_l`|  
  
> [!NOTE]
>  `_toupper_l` 및 `_towupper_l`은 로캘에 종속되지 않으며 직접 호출할 수 없습니다. 이 두 항목은 `_totupper_l` 내부에서 사용하도록 제공됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`toupper`|\<ctype.h>|  
|`_toupper`|\<ctype.h>|  
|`towupper`|\<ctype.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [to 함수](../../c-runtime-library/to-functions.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)   
 [to 함수](../../c-runtime-library/to-functions.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)
