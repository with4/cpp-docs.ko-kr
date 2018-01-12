---
title: "isblank, iswblank, _isblank_l, _iswblank_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
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
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
dev_langs: C++
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5185820e3b8bcb2b5fab1adfaee247743f2e464f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="isblank-iswblank-isblankl-iswblankl"></a>isblank, iswblank, _isblank_l, _iswblank_l
정수가 공백 문자를 나타내는지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int isblank(  
   int c   
);  
int iswblank(  
   wint_t c   
);  
int _isblank_l(  
   int c,  
   _locale_t locale  
);  
int _iswblank_l(  
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
 `c`가 공백 또는 가로 탭 문자의 특정 표현이거나 텍스트 줄 내에서 단어를 구분하는 데 사용되는 로캘별 문자 집합 중 하나인 경우 이러한 각 루틴은 0이 아닌 값을 반환합니다. `c`가 공백 문자(0x20) 또는 가로 탭 문자(0x09)인 경우 `isblank`는 0이 아닌 값을 반환합니다. `isblank` 함수에 대한 테스트 조건의 결과는 로캘의 `LC_CTYPE` 범주 설정에 따라 달라집니다. 자세한 내용은 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘을 사용하고 `_l` 접미사가 있는 버전은 전달된 로캘을 대신 사용한다는 점을 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `c`가 표준 공백 또는 가로 탭 문자에 해당하는 와이드 문자인 경우 `iswblank`는 0이 아닌 값을 반환합니다.  
  
 `isblank` 및 `_isblank_l`의 동작은 `c`가 EOF가 아니거나 0 - 0xFF 범위 내에 포함되지 않는 경우 정의되지 않습니다. 디버그 CRT 라이브러리가 사용되고 `c`가 이러한 값 중 하나가 아닌 경우 함수에서 어설션이 발생합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istblank`|`isblank`|[_ismbcblank](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswblank`|  
|`_istblank_l`|`_isblank_l`|[_ismbcblank_l](../../c-runtime-library/reference/ismbcgraph-functions.md)|`_iswblank_l`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`isblank`|\<ctype.h>|  
|`iswblank`|\<ctype.h> 또는 \<wchar.h>|  
|`_isblank_l`|\<ctype.h>|  
|`_iswblank_l`|\<ctype.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)