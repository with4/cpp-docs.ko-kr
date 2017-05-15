---
title: "mbstowcs_s, _mbstowcs_s_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbstowcs_s_l
- mbstowcs_s
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
- _mbstowcs_s_l
- mbstowcs_s
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 8858827e65ad342f2c48dba26b3be7f7f9dd2ca3
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s, _mbstowcs_s_l
멀티바이트 문자 시퀀스를 해당 와이드 문자 시퀀스로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count   
);  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pReturnValue`  
 변환된 문자 수입니다.  
  
 [out] `wcstr`  
 결과로 변환된 와이드 문자열을 위한 버퍼의 주소입니다.  
  
 [in] `sizeInWords`  
 `wcstr` 버퍼의 크기(단어)입니다.  
  
 [in]`mbstr`  
 null로 끝나는 멀티바이트 문자 시퀀스의 주소입니다.  
  
 [in] `count`  
 `wcstr` 버퍼에 저장할 최대 와이드 문자 수이며, 종결 null 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)를 포함하지 않습니다.  
  
 [in] `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 성공시 0, 실패시 오류 코드.  
  
|오류 조건|반환 값 및 `errno`|  
|---------------------|------------------------------|  
|`wcstr`은 `NULL` 및 `sizeInWords` > 0입니다.|`EINVAL`|  
|`mbstr`가 `NULL`인 경우|`EINVAL`|  
|대상 버퍼가 너무 작아 변환 문자열을 포함할 수 없습니다(`count`가 `_TRUNCATE`가 아닌 경우 아래 설명 참조).|`ERANGE`|  
|`wcstr`이 `NULL`이 아니고 `sizeInWords` == 0임|`EINVAL`|  
  
 이러한 조건 중 하나라도 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 계속해서 실행하도록 허용된 경우 이 함수는 오류 코드를 반환하고 `errno`를 표에 표시된 대로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `mbstowcs_s` 함수는 `mbstr`이 가리키는 멀티바이트 문자열을 `wcstr`이 가리키는 버퍼에 저장된 와이드 문자로 변환합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.  
  
-   멀티바이트 null 문자가 발견되는 경우  
  
-   잘못된 멀티바이트 문자가 발견되는 경우  
  
-   `wcstr` 버퍼에 저장된 와이드 문자의 수가 `count`와 같은 경우  
  
 대상 문자열은 항상 null로 끝납니다(오류 발생 시도 포함).  
  
 `count`가 특수 값 [_TRUNCATE](../../c-runtime-library/truncate.md)이면 `mbstowcs_s`는 대상 버퍼에 포함할 수 있을 만큼 문자열을 최대한 변환하지만 null 종결자를 포함할 공간은 남겨 둡니다.  
  
 `mbstowcs_s`가 소스 문자열을 성공적으로 변환하는 경우 null 종결자를 포함하여 변환된 문자열의 와이드 문자 크기를 `*``pReturnValue`에 배치합니다(`pReturnValue`가 `NULL`이 아닌 경우). `wcstr` 인수가 `NULL`이며 필요한 버퍼 크기를 결정하는 방법을 제공하는 경우에도 발생합니다. `wcstr`이 `NULL`인 경우 `count`가 무시되고 `sizeInWords`는 0이어야 합니다.  
  
 `mbstowcs_s`가 잘못된 멀티바이트 문자를 발견하면 `*``pReturnValue`에 0을 배치하고, 대상 버퍼를 빈 문자열로 설정하며, `errno`를 `EILSEQ`로 설정하고, `EILSEQ`를 반환합니다.  
  
 `mbstr`이 가리키는 시퀀스와 `wcstr`이 가리키는 시퀀스가 겹치는 경우 `mbstowcs_s`의 동작이 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `wcstr` 및 `mbstr`이 겹치지 않고 `count`가 변환할 멀티바이트 문자 수를 정확하게 반영하도록 합니다.  
  
 `mbstowcs_s`는 로캘 종속 동작에 현재 로캘을 사용하고 `_mbstowcs_s_l`은 전달된 로캘을 대신 사용한다는 점을 제외하고는 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`mbstowcs_s`|\<stdlib.h>|  
|`_mbstowcs_s_l`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)
