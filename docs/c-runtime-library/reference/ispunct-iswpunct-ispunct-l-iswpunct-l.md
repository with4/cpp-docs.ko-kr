---
title: "ispunct, iswpunct, _ispunct_l, _iswpunct_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- ispunct
- _iswpunct_l
- iswpunct
- _ispunct_l
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
- iswpunct
- _istpunct
- ispunct
dev_langs:
- C++
helpviewer_keywords:
- _istpunct function
- _ispunct_l function
- iswpunct function
- ispunct function
- istpunct function
- ispunct_l function
- _iswpunct_l function
- iswpunct_l function
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc86de73132dcefc57602586b679b95333c99c2e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="ispunct-iswpunct-ispunctl-iswpunctl"></a>ispunct, iswpunct, _ispunct_l, _iswpunct_l
정수가 문장 부호 문자를 나타내는지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int ispunct(  
   int c   
);  
int iswpunct(  
   wint_t c   
);  
int _ispunct_l(  
   int c,  
   _locale_t locale  
);  
int _iswpunct_l(  
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
 `c`가 문장 부호 문자의 특정 표현인 경우 이러한 각 루틴은 0이 아닌 값을 반환합니다. `ispunct`는 `isalnum`이 0이 아닌 문자 또는 공백 문자가 아닌 모든 인쇄 가능한 문자에 대해 0이 아닌 값을 반환합니다. `iswpunct`는 `iswalnum`이 0이 아닌 와이드 문자도 공백 와이드 문자도 아닌 모든 인쇄 가능한 와이드 문자에 대해 0이 아닌 값을 반환합니다. `c`가 테스트 조건을 만족하지 않는 경우 이러한 루틴은 각각 0을 반환합니다.  
  
 `ispunct` 함수에 대한 테스트 조건의 결과는 로캘의 `LC_CTYPE` 범주 설정에 따라 달라집니다. 자세한 내용은 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘을 사용하고 `_l` 접미사가 있는 버전은 전달된 로캘을 대신 사용한다는 점을 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `ispunct` 및 `_ispunct_l`의 동작은 `c`가 EOF가 아니거나 0 - 0xFF 범위 내에 포함되지 않는 경우 정의되지 않습니다. 디버그 CRT 라이브러리가 사용되고 `c`가 이러한 값 중 하나가 아닌 경우 함수에서 어설션이 발생합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|**_** `istpunct`|`ispunct`|[_ismbcpunct](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswpunct`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`ispunct`|\<ctype.h>|  
|`iswpunct`|\<ctype.h> 또는 \<wchar.h>|  
|`_ispunct_l`|\<ctype.h>|  
|`_iswpunct_l`|\<ctype.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)