---
title: "mbsrtowcs | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- mbsrtowcs
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
- mbsrtowcs
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff120fea2ec3f1ea659233ccee3f66514d0fd76b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="mbsrtowcs"></a>mbsrtowcs
현재 로캘의 멀티바이트 문자열을 해당하는 와이드 문자열로 변환합니다. 이때 멀티바이트 문자의 중간에서 변환을 다시 시작할 수 있습니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [mbsrtowcs_s](../../c-runtime-library/reference/mbsrtowcs-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
size_t mbsrtowcs(  
   wchar_t *wcstr,  
   const char **mbstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t mbsrtowcs(  
   wchar_t (&wcstr)[size],  
   const char **mbstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `wcstr`  
 변환된 결과 와이드 문자열을 저장하는 주소입니다.  
  
 [in, out] `mbstr`  
 변환할 멀티바이트 문자열의 위치에 대한 간접 포인터입니다.  
  
 [in] `count`  
 변환하여 `wcstr`에 저장할 최대 문자(바이트 아님) 수입니다.  
  
 [in, out] `mbstate`  
 `mbstate_t` 변환 상태 개체에 대한 포인터입니다. 이 값이 null 포인터이면 정적 내부 변환 상태 개체가 사용됩니다. 내부 `mbstate_t` 개체는 스레드로부터 안전하지 않으므로 항상 고유한 `mbstate` 매개 변수를 전달하는 것이 좋습니다.  
  
## <a name="return-value"></a>반환 값  
 종결 null 문자(있는 경우)를 포함하지 않고 정상적으로 변환된 문자 수를 반환합니다. 오류가 발생하면 (size_t)(-1)을 반환하고 `errno`를 EILSEQ로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `mbsrtowcs` 함수는 `mbstr`에 포함된 변환 상태를 사용하여 `wcstr`이 간접적으로 가리키는 멀티바이트 문자열을 `mbstate`이 가리키는 버퍼에 저장된 와이드 문자로 변환합니다. 종결 null 멀티바이트 문자가 발견되거나, 현재 로캘에서 올바른 문자에 해당하지 않는 멀티바이트 시퀀스가 발견되거나, `count`개의 문자가 변환될 때까지 각 문자에 대해 변환이 계속됩니다. `mbsrtowcs`는 `count`가 나올 때나 그 전에 멀티바이트 null 문자('\0')를 발견하면 해당 문자를 16비트 종결 null 문자로 변환한 후 중지됩니다.  
  
 따라서 `wcstr`의 와이드 문자열은 `mbsrtowcs`가 변환 중에 멀티바이트 null 문자를 발견하는 경우에만 null로 종결됩니다. `mbstr`이 가리키는 시퀀스와 `wcstr`이 가리키는 시퀀스가 겹치는 경우 `mbsrtowcs`의 동작이 정의되지 않습니다. 현재 로캘의 LC_TYPE 범주가 `mbsrtowcs`에 영향을 줍니다.  
  
 `mbsrtowcs` 함수는 다시 시작할 수 있다는 점에서 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)과 다릅니다. 같거나 다른 다시 시작 가능 함수에 대한 후속 호출에서는 변환 상태가 `mbstate`에 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어 `mbsrlen` 대신 후속 `mbslen` 호출을 사용하는 경우 응용 프로그램은 `mbsrtowcs` 대신 `mbstowcs.`을 사용해야 합니다.  
  
 `wcstr`이 null 포인터가 아닌 경우 종결 null 문자에 도달하여 변환이 중지된 경우 `mbstr`이 가리키는 포인터 개체에는 null 포인터가 할당됩니다. 그렇지 않으면 변환된 마지막 멀티바이트 문자 바로 다음의 주소(있는 경우)가 할당됩니다. 그러므로 후속 함수에서 이 호출이 중지된 변환을 다시 시작할 수 있습니다.  
  
 `wcstr` 인수가 null 포인터이면 `count` 인수는 무시되고 `mbsrtowcs`는 대상 문자열에 대해 필요한 와이드 문자 크기를 반환합니다. `mbstate`가 null 포인터이면 함수는 스레드로부터 안전하지 않은 정적 내부 `mbstate_t` 변환 상태 개체를 사용합니다. 문자 시퀀스 `mbstr`에 해당하는 멀티바이트 문자 표현이 없으면 -1이 반환되며 `errno`가 `EILSEQ`로 설정됩니다.  
  
 `mbstr`이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL` 로 설정하고 -1을 반환합니다.  
  
 C++에서 이 함수는 해당 최신 보안 버전을 호출하는 템플릿 오버로드를 포함합니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
## <a name="exceptions"></a>예외  
 `mbsrtowcs` 함수는 현재 스레드의 함수가 `setlocale`을 호출하지 않고, 이 함수가 실행 중이며, `mbstate` 인수가 null 포인터가 아니면 다중 스레드로부터 안전합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`mbsrtowcs`|\<wchar.h>|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)