---
title: "localeconv | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "localeconv"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "localeconv"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "lconv 형식"
  - "localeconv 함수"
  - "로캘, 정보 가져오기"
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# localeconv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로케일 설정에 자세한 정보를 가져옵니다.  
  
## 구문  
  
```  
  
struct lconv *localeconv( void );  
```  
  
## 반환 값  
 `localeconv`는 [struct lconv](../../c-runtime-library/standard-types.md)타입으로 채워진 오브젝트를 가리키는 포인터를 반환합니다.  개체 내의 값은 `localeconv`의 후속 호출에 의해 덮어 씌여질 수 있고 개체를 직접 수정 하지 않습니다.  `LC_ALL`, `LC_MONETARY`, 또는 `LC_NUMERIC`의 값 `category` 값과 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)는 구조체의 내용을 덮어씁니다.  
  
## 설명  
 `localeconv` 함수는 현재 로케일에 대한 숫자 서식에 대한 자세한 정보를 가져옵니다.  이 정보는 타입 구조체**lconv**에 저장됩니다.  **lconv** 구조체는 LOCALE.H에 정의디고 다음과 같은 멤버를 포함 합니다.  
  
 `char *decimal_point, wchar_t *_W_decimal_point`  
 화폐 수량에 대한 소수점 문자  
  
 `char *thousands_sep, wchar_t *_W_thousands_sep`  
 화폐가 아닌 수량의 소수점 왼쪽의 자릿수를 구분 하는 문자  
  
 `char *grouping`  
 화폐가 아닌 수량에서 각 자릿수 그룹의 크기  
  
 `char *int_curr_symbol, wchar_t *_W_int_curr_symbol`  
 현재 로케일에 대한 국제 통화 기호  처음 세 개의 문자는 *ISO 4217 Codes for the Representation of Currency and Funds* 표준에 정의 된 대로 알파벳 국제 통화 기호를 지정합니다.  네 번째 문자\(null 문자 바로 앞\)는 화폐 수량에서 국제 통화 기호를 구분합니다.  
  
 `char *currency_symbol, wchar_t *_W_currency_symbol`  
 현재 로케일에 대한 로컬 통화 기호  
  
 `char *mon_decimal_point, wchar_t *_W_mon_decimal_point`  
 화폐 수량에 대한 소수점 문자  
  
 `char *mon_thousands_sep, wchar_t *_W_mon_thousands_sep`  
 화폐 수량에서 소수 부분 구분 기호  
  
 `char *mon_grouping`  
 화폐 수량에서 각 자릿수 그룹의 크기  
  
 `char *positive_sign, wchar_t *_W_positive_sign`  
 음수가 아닌 화폐 수량에 대한 기호를 나타내는 문자열  
  
 `char *negative_sign, wchar_t *_W_negative_sign`  
 음수인 화폐 수량에 대한 기호를 나타내는 문자열  
  
 `char int_frac_digits`  
 국제 형식의 화폐수량에서 소수점 오른쪽의 자릿 수  
  
 `char frac_digits`  
 국제 형식의 화폐수량에서 소수점 오른쪽의 자릿 수  
  
 `char p_cs_precedes`  
 음수가 아닌 형식의 화폐 수량의 앞에 나타나는 통화 기호는 1로 설정합니다.  기호가 값을 따른다면 0으로 설정합니다.  
  
 `char p_sep_by_space`  
 음수가 아닌 형식의 화폐수량에서 통화 기호가 공백으로 구분되는 경우, 1로 설정 합니다.  공백으로 분리되지 않는 경우 0으로 설정합니다.  
  
 `char n_cs_precedes`  
 음수 형식의 화폐 수량에서 통화 기호가 값의 앞에 나타날 경우 1로 설정합니다.  기호가 값에 성공 하면 0으로 설정 합니다.  
  
 `char n_sep_by_space`  
 음수 형식의 화폐수량에서 통화 기호가 값에서 공백으로 구분되는 경우, 1로 설정 합니다.  공백으로 분리되지 않는 경우 0으로 설정합니다.  
  
 `char p_sign_posn`  
 음수가 아닌 형식의 화폐 수량 양수 부호의 위치  
  
 `char n_sign_posn`  
 음수 형식의 화폐 수량 양수 부호의 위치  
  
 구조체의 요소 `char` `*` 및 `wchar_t *` 버전은 문자열에 대한 포인터입니다.  `""` \(또는 `wchar_t *`에 대한 `L""`\)와 같은 이러한 것들은 길이가 0이거나 현재 로케일에서 지원 되지 않습니다.  `decimal_point`와 `_W_decimal_point`는 항상 지원되고 0이 아닌 길이를 가집니다.  
  
 구조체의 멤버 `char`는 문자와 음수가 아닌 작은 숫자입니다.  **CHAR\_MAX**와 같은 이러한 것들은 현재 로케일에서 지원 되지 않습니다.  
  
 **grouping** 과 **mon\_grouping**의 요소는 다음 규칙에 따라 해석 됩니다.  
  
 **CHAR\_MAX**  
 그룹화를 수행 하지 마십시오.  
  
 0  
 각 나머지 자릿 수에 대해 이전의 요소를 사용하십시오.  
  
 *n*  
 현재 그룹을 구성 하는 자릿 수의 수  현재 그룹 자릿수 그룹전에 다음 자릿 수 그룹의 크기를 결정 하려면 다음 요소를 검사 합니다.  
  
 **int\_curr\_symbol**에 대한 값들은 다음 규칙에 따라 해석 됩니다.  
  
-   처음 세 개의 문자는 *ISO 4217 Codes for the Representation of Currency and Funds* 표준에 정의 된 대로 알파벳 국제 통화 기호를 지정합니다.  
  
-   네 번째 문자 \(null문자 바로 앞에\)는 화폐 수량에서 국제 통화 기호를 구분 합니다.  
  
 **p\_cs\_precedes** 과 **n\_cs\_precedes**에 대한 값들은 다음 규칙에 따라 해석 됩니다.\(해당 **n\_cs\_precedes**규칙은 괄호 안에\):  
  
 0  
 통화 기호는 음수가 아닌\(음수인\) 형식화된 금전적 가치를 따릅니다.  
  
 1  
 통화 기호는 음수가 아닌\(음수인\) 형식화된 금전적 가치의 앞에 나타납니다.  
  
 **p\_sep\_by\_space** 과 **n\_sep\_by\_space**에 대한 값들은 다음 규칙에 따라 해석 됩니다 \(해당 **n\_sep\_by\_space** 규칙은 괄호 안에\):  
  
 0  
 음수가 아닌\(음수인\) 형식화된 통화 기호에서 통화 기호는 공백에 의해 값에서 분리됩니다.  
  
 1  
 음수가 아닌\(음수인\) 형식화된 금전적 가치에서 통화 기호와 값은 공백으로 구분되지 않습니다.  
  
 **p\_sign\_posn** 와 **n\_sign\_posn**에 대한 값들은 는 다음 규칙에 따라 해석됩니다.  
  
 0  
 괄호는 수량 및 통화 기호를 묶습니다.  
  
 1  
 기호 문자열은 수량 및 통화 기호 앞에 나타납니다.  
  
 2  
 기호 문자열은 수량 및 통화 기호를 따릅니다.  
  
 3  
 기호 문자열은 통화 기호의 바로 앞에 나타납니다.  
  
 4  
 기호 문자열은 통화 기호 바로 뒤에 나타납니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`localeconv`|\<locale.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 참고 항목  
 [로캘](../../c-runtime-library/locale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)