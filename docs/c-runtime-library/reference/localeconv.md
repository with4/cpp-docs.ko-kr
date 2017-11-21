---
title: "localeconv | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: localeconv
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
f1_keywords: localeconv
dev_langs: C++
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aa001a4c8dde1337eb576ae3a2c78108e4cb3199
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="localeconv"></a>localeconv
로캘 설정에 대한 자세한 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct lconv *localeconv( void );  
```  
  
## <a name="return-value"></a>반환 값  
 `localeconv`는 [struct lconv](../../c-runtime-library/standard-types.md) 형식의 채워진 개체에 대한 포인터를 반환합니다. 개체에 포함 된 값 스레드 로컬 저장소의 로캘 설정에서 복사 되 고 후속 호출에 의해 덮어쓸 수 있는 `localeconv`합니다. 이 개체의 값에 대 한 변경 내용을 로캘 설정을 수정 하지 마십시오. `LC_ALL`, `LC_MONETARY` 또는 `LC_NUMERIC`의 `category` 값을 사용하여 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 호출하면 구조체의 콘텐츠를 덮어씁니다.  
  
## <a name="remarks"></a>설명  
 `localeconv` 함수는 현재 로캘의 숫자 형식에 대한 자세한 정보를 가져옵니다. 이 정보 형식의 구조에 저장 됩니다 `lconv`합니다. `lconv` 로캘에 정의 된 구조입니다. H에 다음 멤버가 포함 되어 있습니다.  
  
 `char *decimal_point, wchar_t *_W_decimal_point`  
 비통화 수량에 대한 소수점 문자입니다.  
  
 `char *thousands_sep, wchar_t *_W_thousands_sep`  
 비통화 수량에 대한 소수점 왼쪽의 숫자 그룹을 구분하는 문자입니다.  
  
 `char *grouping`  
 에 대 한 포인터는 `char`-자릿수 nonmonetary 수량에 각 그룹의 크기를 포함 하는 정수 크기입니다.  
  
 `char *int_curr_symbol, wchar_t *_W_int_curr_symbol`  
 현재 로캘에 대한 국제 통화 기호입니다. 처음 세 문자는 *ISO 4217 Codes for the Representation of Currency and Funds* 표준에 정의된 대로 영문자 국제 통화 기호를 지정합니다. 네 번째 문자(null 문자 바로 앞)는 통화 수량에서 국제 통화 기호를 구분합니다.  
  
 `char *currency_symbol, wchar_t *_W_currency_symbol`  
 현재 로캘에 대한 현지 통화 기호입니다.  
  
 `char *mon_decimal_point, wchar_t *_W_mon_decimal_point`  
 통화 수량에 대한 소수점 문자입니다.  
  
 `char *mon_thousands_sep, wchar_t *_W_mon_thousands_sep`  
 통화 수량에서 소수점 왼쪽의 숫자 그룹에 대한 구분 기호입니다.  
  
 `char *mon_grouping`  
 에 대 한 포인터는 `char`-자릿수 통화 수량에 각 그룹의 크기를 포함 하는 정수 크기입니다.  
  
 `char *positive_sign, wchar_t *_W_positive_sign`  
 음수가 아닌 통화 수량에 대한 부호를 나타내는 문자열입니다.  
  
 `char *negative_sign, wchar_t *_W_negative_sign`  
 음수 통화 수량에 대한 부호를 나타내는 문자열입니다.  
  
 `char int_frac_digits`  
 국제적으로 서식이 지정된 통화 수량에서 소수점 오른쪽의 자릿수입니다.  
  
 `char frac_digits`  
 서식이 지정된 통화 수량에서 소수점 오른쪽의 자릿수입니다.  
  
 `char p_cs_precedes`  
 통화 기호가 음수가 아닌 서식이 지정된 통화 수량에 대한 값보다 앞에 오면 1로 설정합니다. 기호가 값 다음에 오면 0으로 설정합니다.  
  
 `char p_sep_by_space`  
 통화 기호가 음수가 아닌 서식이 지정된 통화 수량에 대한 값에서 공백으로 구분되면 1로 설정합니다. 공백으로 구분되지 않으면 0으로 설정합니다.  
  
 `char n_cs_precedes`  
 통화 기호가 음수 서식이 지정된 통화 수량에 대한 값보다 앞에 오면 1로 설정합니다. 기호가 값 다음에 오면 0으로 설정합니다.  
  
 `char n_sep_by_space`  
 통화 기호가 음수 서식이 지정된 통화 수량에 대한 값에서 공백으로 구분되면 1로 설정합니다. 공백으로 구분되지 않으면 0으로 설정합니다.  
  
 `char p_sign_posn`  
 음수가 아닌 서식이 지정된 통화 수량에서 양수 부호의 위치입니다.  
  
 `char n_sign_posn`  
 음수 서식이 지정된 통화 수량에서 양수 부호의 위치입니다.  
  
지정 된, 멤버로 제외 하 고는 `lconv` 있는 구조 `char *` 및 `wchar_t *` 버전은 문자열에 대 한 포인터입니다. `""`(또는 `wchar_t *`의 경우 `L""`)과 같은 이러한 멤버는 길이가 0이거나 현재 로캘에서 지원되지 않습니다. `decimal_point` 및 `_W_decimal_point`는 항상 지원되며 길이가 0이 아닙니다.  
  
구조체의 `char` 멤버는 음수가 아닌 작은 숫자이며 문자가 아닙니다. 해당 하는 이러한 `CHAR_MAX` 현재 로컬에서 지원 되지 않습니다.  
  
값 `grouping` 및 `mon_grouping` 다음 규칙에 따라 해석 됩니다.  
  
- `CHAR_MAX`-추가 그룹화를 수행 하지 마십시오.  
  
- 0-각 나머지 자릿수에 대 한 이전 요소를 사용 합니다.  
  
- *n*-현재 그룹을 구성 하는 숫자의 수입니다. 다음 요소를 검사하여 현재 그룹 앞 다음 숫자 그룹의 크기를 확인합니다.  
  
에 대 한 값 `int_curr_symbol` 다음 규칙에 따라 해석 됩니다.  
  
-   처음 세 문자는 *ISO 4217 Codes for the Representation of Currency and Funds* 표준에 정의된 대로 영문자 국제 통화 기호를 지정합니다.  
  
-   네 번째 문자(null 문자 바로 앞)는 통화 수량에서 국제 통화 기호를 구분합니다.  
  
에 대 한 값 `p_cs_precedes` 및 `n_cs_precedes` 다음 규칙에 따라 해석 (의 `n_cs_precedes` 규칙은 괄호 안에 있음):  
  
- 통화 기호는 0-(음수) 음이 아닌 형식이 지정 된 통화 값에 대 한 값을 따릅니다.  
  
- 1-통화 기호 앞 음수가 아닌 (음수) 형식이 지정 된 통화 값에 대 한 값을 표시 됩니다.  
  
에 대 한 값 `p_sep_by_space` 및 `n_sep_by_space` 다음 규칙에 따라 해석 (의 `n_sep_by_space` 규칙은 괄호 안에 있음):  
  
- 0-(음수) 음이 아닌 형식이 지정 된 통화 값에 대 한 공간으로 값에서 통화 기호 분리 됩니다.  
  
- 1-통화 기호 및 음수가 아닌 (음수) 형식이 지정 된 통화 값에 대 한 값 사이의 공간 분리 되지 않습니다.  
  
에 대 한 값 `p_sign_posn` 및 `n_sign_posn` 다음 규칙에 따라 해석 됩니다.  
  
- 0-괄호 수량 및 통화 기호를 묶습니다.  
  
- 1-sign 문자열 수량 및 통화 기호를 앞에 옵니다.  
  
- 2) 기호 (+ 문자열 수량 및 통화 기호는 다음과 같습니다.  
  
- 3-기호 문자열에 통화 기호 바로 앞에 있습니다.  
  
- 4-기호 즉시 다음과 통화 기호는 문자열입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`localeconv`|\<locale.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [로캘](../../c-runtime-library/locale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)