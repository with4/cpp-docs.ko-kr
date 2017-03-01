---
title: "mbsrtowcs_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbsrtowcs_s
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
- mbsrtowcs_s
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 440cf44dda47253141247fe9a82925e13c84b48f
ms.lasthandoff: 02/24/2017

---
# <a name="mbsrtowcss"></a>mbsrtowcs_s
현재 로캘의 멀티바이트 문자열을 와이드 문자열 표현으로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t * wcstr,  
   size_t sizeInWords,  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
);  
template <size_t size>  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pReturnValue`  
 변환된 문자 수입니다.  
  
 [out] `wcstr`  
 결과로 생성되는 와이드 문자열을 저장할 버퍼의 주소입니다.  
  
 [out] `sizeInWords`  
 단어 단위의 `wcstr` 크기(와이드 문자)입니다.  
  
 [in, out] `mbstr`  
 변환할 멀티바이트 문자열의 위치에 대한 간접 포인터입니다.  
  
 [in] `count`  
 `wcstr` 버퍼에 저장할 최대 와이드 문자 수이며, 종결 null 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)를 포함하지 않습니다.  
  
 [in, out] `mbstate`  
 `mbstate_t` 변환 상태 개체에 대한 포인터입니다. 이 값이 null 포인터이면 정적 내부 변환 상태 개체가 사용됩니다. 내부 `mbstate_t` 개체는 스레드로부터 안전하지 않으므로 항상 고유한 `mbstate` 매개 변수를 전달하는 것이 좋습니다.  
  
## <a name="return-value"></a>반환 값  
 변환이 완료되면&0;이 반환되고, 실패하면 오류 코드가 반환됩니다.  
  
|오류 조건|반환 값 및 `errno`|  
|---------------------|------------------------------|  
|`wcstr`이 null 포인터이고 `sizeInWords`가 0보다 큰 경우|`EINVAL`|  
|`mbstr`이 null 포인터인 경우|`EINVAL`|  
|
          `mbstr`가 간접적으로 가리키는 문자열이 현재 로캘에 대해 잘못된 멀티바이트 시퀀스를 포함하는 경우|`EILSEQ`|  
|대상 버퍼가 너무 작아서 변환된 문자열을 포함할 수 없는 경우(`count`가 `_TRUNCATE`인 경우는 제외. 자세한 내용은 설명 참조)|`ERANGE`|  
  
 이러한 상황 중 하나라도 발생하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 계속해서 실행하도록 허용된 경우 이 함수는 오류 코드를 반환하고 `errno`를 표에 표시된 대로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `mbsrtowcs_s` 함수는 `mbstr`에 포함된 변환 상태를 사용하여 `wcstr`이 간접적으로 가리키는 멀티바이트 문자열을 `mbstate`이 가리키는 버퍼에 저장된 와이드 문자로 변환합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.  
  
-   멀티바이트 null 문자가 발견되는 경우  
  
-   잘못된 멀티바이트 문자가 발견되는 경우  
  
-   `wcstr` 버퍼에 저장된 와이드 문자의 수가 `count`와 같은 경우  
  
 `wcstr`이 null 포인터인 경우를 제외하면 오류가 발생하더라도 대상 문자열 `wcstr`은 항상 null로 종결됩니다.  
  
 `count`가 특수 값 [_TRUNCATE](../../c-runtime-library/truncate.md)이면 `mbsrtowcs_s`는 대상 버퍼에 포함할 수 있을 만큼 문자열을 최대한 변환하지만 null 종결자를 포함할 공간은 남겨 둡니다.  
  
 `mbsrtowcs_s`는 소스 문자열을 정상적으로 변환하는 경우 변환된 문자열의 와이드 문자 크기와 null 종결자를 `*``pReturnValue`에 배치합니다. 이 경우 `pReturnValue`는 null 포인터가 아니어야 합니다. 이 작업은 `wcstr` 인수가 null 포인터인 경우에도 수행되므로 필요한 버퍼 크기를 결정할 수 있습니다. `wcstr`이 null 포인터이면 `count`는 무시됩니다.  
  
 `wcstr`이 null 포인터가 아닌 경우 종결 null 문자에 도달하여 변환이 중지된 경우 `mbstr`이 가리키는 포인터 개체에는 null 포인터가 할당됩니다. 그렇지 않으면 변환된 마지막 멀티바이트 문자 바로 다음의 주소(있는 경우)가 할당됩니다. 그러므로 후속 함수에서 이 호출이 중지된 변환을 다시 시작할 수 있습니다.  
  
 `mbstate`가 null 포인터이면 라이브러리 내부 `mbstate_t` 변환 상태 정적 개체가 사용됩니다. 이 내부 정적 개체가 스레드로부터 안전하지 않으면 고유한 `mbstate` 값을 전달하는 것이 좋습니다.  
  
 `mbsrtowcs_s`는 현재 로캘에서 잘못된 멀티바이트 문자를 발견하면 `*``pReturnValue`에 -1을 배치하고, 대상 버퍼 `wcstr`을 빈 문자열로 설정하며, `errno`를 `EILSEQ`로 설정하고 `EILSEQ`를 반환합니다.  
  
 `mbstr`이 가리키는 시퀀스와 `wcstr`이 가리키는 시퀀스가 겹치는 경우 `mbsrtowcs_s`의 동작이 정의되지 않습니다. 현재 로캘의 LC_TYPE 범주가 `mbsrtowcs_s`에 영향을 줍니다.  
  
> [!IMPORTANT]
>  `wcstr` 및 `mbstr`이 겹치지 않고 `count`가 변환할 멀티바이트 문자 수를 정확하게 반영하도록 합니다.  
  
 `mbsrtowcs_s` 함수는 다시 시작할 수 있다는 점에서 [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)과 다릅니다. 같거나 다른 다시 시작 가능 함수에 대한 후속 호출에서는 변환 상태가 `mbstate`에 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어 `mbsrlen` 대신 후속 `mbslen` 호출을 사용하는 경우 응용 프로그램은 `mbsrtowcs_s` 대신 `mbstowcs_s.`을 사용해야 합니다.  
  
 C++에서는 템플릿 오버로드로 이러한 함수를 간편하게 사용할 수 있습니다. 즉, 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 또한 기존의 비보안 함수를 그에 해당하는 안전한 최신 함수로 자동 교체할 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
## <a name="exceptions"></a>예외  
 `mbsrtowcs_s` 함수는 현재 스레드의 함수가 `setlocale`을 호출하지 않고, 이 함수가 실행 중이며, `mbstate` 인수가 null 포인터가 아니면 다중 스레드로부터 안전합니다.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`mbsrtowcs_s`|\<wchar.h>|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)
