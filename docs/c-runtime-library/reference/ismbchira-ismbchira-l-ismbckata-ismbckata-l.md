---
title: "_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ismbckata
- _ismbchira_l
- _ismbchira
- _ismbckata_l
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
- ismbckata_l
- _ismbckata_l
- ismbckata
- ismbchira
- _ismbckata
- ismbchira_l
- _ismbchira_l
- _ismbchira
dev_langs:
- C++
helpviewer_keywords:
- _ismbckata function
- _ismbchira function
- _ismbckata_l function
- Katakana
- ismbchira function
- _ismbchira_l function
- ismbchira_l function
- ismbdkata_l function
- Hiragana
- ismbckata function
ms.assetid: 2db388a2-be31-489b-81c8-f6bf3f0582d3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38fe65f2b81def4afe08339f38b00cd69702fd83
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="ismbchira-ismbchiral-ismbckata-ismbckatal"></a>_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l
**코드 페이지 932 관련 함수**  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 참조 [CRT 함수는 유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _ismbchira(  
   unsigned int c   
);  
int _ismbchira_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbckata(  
   unsigned int c   
);  
int _ismbckata_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 테스트할 문자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 이러한 각 루틴은 이 문자가 테스트 조건을 만족하는 경우 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다. `c`가 <= 255이고 해당 `_ismbb` 루틴(예를 들어 `_ismbcalnum`은 `_ismbbalnum`에 해당됨)이 있는 경우 결과는 해당 `_ismbb` 루틴의 반환 값입니다.  
  
## <a name="remarks"></a>설명  
 이러한 각 함수는 지정한 조건에 대해 주어진 멀티바이트 문자를 테스트합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
|루틴에서 반환된 값|테스트 조건(코드 페이지 932만 해당)|  
|-------------|-------------------------------------------|  
|`_ismbchira`|더블바이트 히라가나: 0x829F<=`c`<=0x82F1.|  
|`_ismbchira_l`|더블바이트 히라가나: 0x829F<=`c`<=0x82F1.|  
|`_ismbckata`|더블바이트 가타카나: 0x8340<=`c`<=0x8396.|  
|`_ismbckata_l`|더블바이트 가타카나: 0x8340<=`c`<=0x8396.|  
  
 **최종 코드 페이지 932 관련**  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_ismbchira`|\<mbstring.h>|  
|`_ismbchira_l`|\<mbstring.h>|  
|`_ismbckata`|\<mbstring.h>|  
|`_ismbckata_l`|\<mbstring.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [_ismbc 루틴](../../c-runtime-library/ismbc-routines.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)