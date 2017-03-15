---
title: "_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
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
- mbcjistojms
- _mbcjistojms
- _mbcjistojms_l
- _mbcjmstojis_l
- _mbcjmstojis
- mbcjmstojis_l
- mbcjistojms_l
- mbcjmstojis
dev_langs:
- C++
helpviewer_keywords:
- _mbcjmstojis_l function
- _mbcjistojms function
- mbcjmstojis function
- _mbcjistojms_l function
- _mbcjmstojis function
- mbcjistojms function
- mbcjmstojis_l function
- mbcjistojms_l function
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
caps.latest.revision: 20
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
ms.openlocfilehash: 60a870b9c0beff704511ab788d621b0f9697ed5d
ms.lasthandoff: 02/24/2017

---
# <a name="mbcjistojms-mbcjistojmsl-mbcjmstojis-mbcjmstojisl"></a>_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
JIS(Japan Industry Standard)와 JMS(일본 Microsoft) 문자 간을 변환합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned int _mbcjistojms(  
   unsigned int c   
);  
unsigned int _mbcjistojms_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbcjmstojis(  
   unsigned int c   
);  
unsigned int _mbcjmstojis_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 변환할 문자입니다.  
  
 `local`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 일본어 로캘에서 이러한 함수는 변환된 문자를 반환하거나 변환할 수 없는 경우 0을 반환합니다. 일본어가 아닌 다른 언어 로캘에서 이러한 함수는 전달된 문자를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_mbcjistojms` 함수는 JIS(Japan Industry Standard) 문자를 Microsoft 간지(Shift JIS) 문자로 변환합니다. 문자는 선행 및 후행 바이트가 0x21 - 0x7E 범위 내에 있는 경우에만 변환됩니다. 선행 또는 후행 바이트가 이 범위를 벗어나는 경우 `errno`가 `EILSEQ`로 설정됩니다. 이 오류 코드 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 `_mbcjmstojis` 함수는 Shift JIS 문자를 JIS 문자를 변환합니다. 문자는 선행 바이트가 0x81 – 0x9F 또는 0xE0 – 0xFC 범위 내에 있고 후행 바이트가 0x40 – 0x7E 또는 0x80 – 0xFC 범위 내에 있는 경우에만 변환됩니다. 해당 범위의 일부 코드 포인트에는 할당된 문자가 없으므로 변환할 수 없습니다.  
  
 `c` 값은 상위 8비트는 변환할 문자의 선행 바이트를 나타내고 하위 8비트는 후행 바이트를 나타내는 16비트 값이어야 합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 이전 버전에서는 `_mbcjistojms` 및 `_mbcjmstojis`를 각각 `jistojms` 및 `jmstojis`라고 했습니다. `_mbcjistojms`,`_mbcjistojms_l`,`_mbcjmstojis` 및 `_mbcjmstojis_l`을 대신 사용해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_mbcjistojms`|\<mbstring.h>|  
|`_mbcjistojms_l`|\<mbstring.h>|  
|`_mbcjmstojis`|\<mbstring.h>|  
|`_mbcjmstojis_l`|\<mbstring.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)
