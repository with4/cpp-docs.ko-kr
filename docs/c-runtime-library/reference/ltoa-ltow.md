---
title: "_ltoa, _ltow | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ltoa
- _ltow
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
- ltow
- _ltot
- _ltoa
- _ltow
dev_langs:
- C++
helpviewer_keywords:
- converting integers
- _ltoa function
- _ltow function
- ltow function
- ltoa function
- long integer conversion to string
- converting numbers, to strings
ms.assetid: 14036104-2c25-4759-87c0-918ed8521e47
caps.latest.revision: 17
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
ms.openlocfilehash: 5e67ca683ac8946f88389e9ca2323f1255da6695
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="ltoa-ltow"></a>_ltoa, _ltow
long 정수를 문자열로 변환합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_ltoa_s, _ltow_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
char *_ltoa(  
   long value,  
   char *str,  
   int radix   
);  
wchar_t *_ltow(  
   long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ltoa(  
   long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ltow(  
   long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value`  
 변환할 숫자입니다.  
  
 `str`  
 결과 문자열입니다.  
  
 `radix`  
 `value`의 기본입니다.  
  
## <a name="return-value"></a>반환 값  
 이러한 각 함수는 `str`에 대한 포인터를 반환합니다. 반환되는 오류가 없습니다.  
  
## <a name="remarks"></a>설명  
 `_ltoa` 함수는 `value`의 숫자를 null로 끝나는 문자열로 변환하고 결과(최대 33바이트)를 `str`에 저장합니다. `radix` 인수 기본을 지정 `value`, 2-36 범위에 이어야 합니다. 경우 `radix` 이 10 및 `value` 가 음수인 경우 저장된 된 문자열의 첫 번째 문자는 빼기 기호 (-). `_ltow`는 `_ltoa`의 와이드 문자 버전입니다. `_ltow`의 두 번째 인수 및 반환 값은 와이드 문자열입니다. 이러한 각 함수는 Microsoft 지정입니다.  
  
> [!IMPORTANT]
>  버퍼 오버런을 방지하려면 `str` 버퍼가 변환된 숫자와 후행 null 문자 및 부호 문자를 포함할 만큼 충분히 커야 합니다.  
  
 C++에서 이러한 함수에는 템플릿 오버로드가 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_ltoa`|\<stdlib.h>|  
|`_ltow`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)에 대한 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md)
