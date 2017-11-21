---
title: _vscprintf_p, _vscprintf_p_l, _vscwprintf_p, _vscwprintf_p_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _vscprintf_p_l
- _vscprintf_p
- _vscwprintf_p_l
- _vscwprintf_p
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
- _vscprintf_p
- _vscprintf_p_l
- vscwprintf_p
- vscprintf_p
- vscwprintf_p_l
- _vscwprintf_p_l
- vscprintf_p_l
- _vscwprintf_p
dev_langs: C++
helpviewer_keywords:
- vscprintf_p function
- _vsctprintf_p_l function
- vscwprintf_p_l function
- _vscwprintf_p_l function
- _vscprintf_p function
- vsctprintf_p function
- _vscprintf_p_l function
- _vscwprintf_p function
- vscwprintf_p function
- vsctprintf_p_l function
- _vsctprintf_p function
- vscprintf_p_l function
ms.assetid: 5da920b3-8652-4ee9-b19e-5aac3ace9d03
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 465260a07a6e18922a67cbb12f3e36b75f60e51a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="vscprintfp-vscprintfpl-vscwprintfp-vscwprintfpl"></a>_vscprintf_p, _vscprintf_p_l, _vscwprintf_p, _vscwprintf_p_l
인수가 사용되는 순서를 지정하는 기능과 함께 인수 목록에 대한 포인터를 사용하여 형식이 지정된 문자열의 문자 수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _vscprintf_p(  
   const char *format,  
   va_list argptr   
);  
int _vscprintf_p _l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vscwprintf_p (  
   const wchar_t *format,  
   va_list argptr   
);  
int _vscwprintf_p _l(  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `argptr`  
 인수 목록에 대한 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.  
  
## <a name="return-value"></a>반환 값  
 `_vscprintf_p`는 인수 목록에서 가리키는 문자열이 지정된 형식 지정 코드를 사용하여 인쇄되거나 파일 또는 버퍼로 보내진 경우 생성될 문자 수를 반환합니다. 반환된 값은 종료 null 문자를 포함하지 않습니다. `_vscwprintf_p`는 와이드 문자에 대해 동일한 기능을 수행합니다.  
  
## <a name="remarks"></a>설명  
 이러한 함수와 `_vscprintf` 및 `_vscwprintf`의 차이점은 인수가 사용되는 순서를 지정하는 기능을 지원한다는 것뿐입니다. 자세한 내용은 [printf_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)를 참조하세요.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 `format`이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이러한 함수가 -1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열인 경우 이는 null로 종료되고 올바른 수와 형식의 매개 변수를 사용합니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vsctprintf_p`|`_vscprintf_p`|`_vscprintf_p`|`_vscwprintf_p`|  
|`_vsctprintf_p_l`|`_vscprintf_p_l`|`_vscprintf_p_l`|`_vscwprintf_p_l`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_vscprintf_p`, `_vscprintf_p_l`|\<stdio.h>|  
|`_vscwprintf_p`, `_vscwprintf_p_l`|\<stdio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [vsprintf](../../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [_scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l](../../c-runtime-library/reference/scprintf-p-scprintf-p-l-scwprintf-p-scwprintf-p-l.md)   
 [_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l](../../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)