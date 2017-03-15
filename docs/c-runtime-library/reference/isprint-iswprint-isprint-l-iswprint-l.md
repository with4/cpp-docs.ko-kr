---
title: "isprint, iswprint, _isprint_l, _iswprint_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iswprint
- isprint
- _isprint_l
- _iswprint_l
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
- iswprint
- _istprint
- isprint
dev_langs:
- C++
helpviewer_keywords:
- _istprint function
- iswprint function
- _iswprint_l function
- isprint_l function
- istprint function
- isprint function
- iswprint_l function
- _isprint_l function
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3836d13d9f050ebdd7ed7502e11bbde2da76992a
ms.lasthandoff: 02/24/2017

---
# <a name="isprint-iswprint-isprintl-iswprintl"></a>isprint, iswprint, _isprint_l, _iswprint_l
정수가 인쇄 가능한 문자를 나타내는지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int isprint(  
   int c   
);  
int iswprint(  
   wint_t c   
);  
int _isprint_l(  
   int c,  
   _locale_t locale  
);  
int _iswprint_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 테스트할 정수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `c`가 인쇄 가능한 문자의 특정 표현인 경우 이러한 각 루틴은&0;이 아닌 값을 반환합니다. `c`가 공백 문자(0x20 – 0x7E)를 포함하여 인쇄 가능한 문자인 경우 `isprint`는 0이 아닌 값을 반환합니다. `c`가 공백 와이드 문자를 포함하여 인쇄 가능한 와이드 문자인 경우 `iswprint`는&0;이 아닌 값을 반환합니다. `c`가 테스트 조건을 만족하지 않는 경우 이러한 루틴은 각각 0을 반환합니다.  
  
 이러한 함수에 대한 테스트 조건의 결과는 로캘의 `LC_CTYPE` 범주 설정에 따라 달라집니다. 자세한 내용은 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)를 참조하세요. `_l` 접미사가 없는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘을 사용하고 `_l` 접미사가 있는 버전은 전달된 로캘을 대신 사용한다는 점을 제외하고는 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `isprint` 및 `_isprint_l`의 동작은 `c`가 EOF가 아니거나 0 - 0xFF 범위 내에 포함되지 않는 경우 정의되지 않습니다. 디버그 CRT 라이브러리가 사용되고 `c`가 이러한 값 중 하나가 아닌 경우 함수에서 어설션이 발생합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_unicode 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|**_** `istprint`|`isprint`|[_ismbcprint](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswprint`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`isprint`|\<ctype.h>|  
|`iswprint`|\<ctype.h> 또는 \<wchar.h>|  
|`_isprint_l`|\<ctype.h>|  
|`_iswprint_l`|\<ctype.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)
