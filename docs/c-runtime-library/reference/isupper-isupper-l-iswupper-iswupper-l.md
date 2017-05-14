---
title: "isupper, _isupper_l, iswupper, _iswupper_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- isupper
- iswupper
- _iswupper_l
- _isupper_l
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
- isupper
- _istupper
- iswupper
dev_langs:
- C++
helpviewer_keywords:
- istupper function
- iswupper function
- isupper_l function
- _isupper_l function
- iswupper_l function
- _istupper function
- _iswupper_l function
- isupper function
ms.assetid: da2bcc9f-241c-48c0-9a0e-ad273827e16a
caps.latest.revision: 21
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
ms.openlocfilehash: ded3f62cc54e769e9b7ba17bd106a64daf14e63f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="isupper-isupperl-iswupper-iswupperl"></a>isupper, _isupper_l, iswupper, _iswupper_l
정수가 대문자를 나타내는지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int isupper(  
   int c   
);  
int _isupper_l (  
   int c,  
   _locale_t locale  
);  
int iswupper(  
   wint_t c   
);  
int _iwsupper_l(  
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
 `c`가 대문자의 특정 표현인 경우 이러한 각 루틴은 0이 아닌 값을 반환합니다. `isupper`0이 아닌 값을 반환 `c` 대문자 (A ~ Z)가 있습니다. `iswupper`은 `c`가 대문자에 해당하는 와이드 문자인 경우 또는 `c`가 `iswcntrl`, `iswdigit`, `iswpunct` 또는 `iswspace`가 0인 구현에서 정의된 와이드 문자 집합 중 하나인 경우 0이 아닌 값을 반환합니다. `c`가 테스트 조건을 만족하지 않는 경우 이러한 루틴은 각각 0을 반환합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘 대신 전달된 로캘을 사용합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `isupper` 및 `_isupper_l`의 동작은 `c`가 EOF가 아니거나 0 - 0xFF 범위 내에 포함되지 않는 경우 정의되지 않습니다. 디버그 CRT 라이브러리가 사용되고 `c`가 이러한 값 중 하나가 아닌 경우 함수에서 어설션이 발생합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istupper`|`isupper`|[_ismbcupper](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`iswupper`|  
|`_istupper_l`|`_isupper_l`|[_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`_iswupper_l`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`isupper`|\<ctype.h>|  
|`_isupper_l`|\<ctype.h>|  
|`iswupper`|\<ctype.h> 또는 \<wchar.h>|  
|`_iswupper_l`|\<ctype.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)
