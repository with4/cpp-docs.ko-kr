---
title: "strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strxfrm"
  - "_wcsxfrm_l"
  - "_strxfrm_l"
  - "wcsxfrm"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strxfrm"
  - "_tcsxfrm"
  - "wcsxfrm"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strxfrm_l 함수"
  - "_tcsxfrm 함수"
  - "_wcsxfrm_l 함수"
  - "문자열 비교[C++], 문자열 변환"
  - "문자열[C++], 로캘 비교"
  - "strxfrm 함수"
  - "strxfrm_l 함수"
  - "tcsxfrm 함수"
  - "wcsxfrm 함수"
  - "wcsxfrm_l 함수"
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로캘 지정 정보를 기반으로 문자열을 변환합니다.  
  
## 구문  
  
```  
size_t strxfrm(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
size_t wcsxfrm(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
size_t _strxfrm_l(  
   char *strDest,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
size_t wcsxfrm_l(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `strDest`  
 대상 문자열입니다.  
  
 `strSource`  
 소스 문자열입니다.  
  
 `count`  
 `strDest`에 위치할 최대 문자 수입니다*.*  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 변환된 문자열의 길이를 null 종결 문자를 포함하지 않고 반환합니다.  반환값이 `count`보다 크거나 같으면 `strDest`의 내용은 예측할 수 없습니다.  오류에서, 각 함수는 `errno`를 설정하고 `INT_MAX`를 반환합니다.  잘못된 문자의 경우, `errno`는 `EILSEQ`로 설정됩니다.  
  
## 설명  
 `strxfrm` 함수는 `strSource`에 의해 가리켜지는 문자열을 `strDest`에 저장된 새로운 대조된 형식으로 전환합니다.  null 문자를 포함하여 `count` 문자보다 더 변환되지 않고 결과 문자열에 저장됩니다.  로캘의 `LC_COLLATE` 범주 설정을 사용하여 변환이 일어납니다.  `LC_COLLATE` 에 대한 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 를 참조하십시오.  `strxfrm`는 로캘 종속인 동작에 현재 로캘을 사용합니다. 현재 로캘 대신 전달된 로캘을 사용한다는 것을 제외하면 `_strxfrm_l`는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 변환 이후 변형된 문자열 두 개를 사용한 `strcmp`의 호출은 두 원본 문자열을 적용한 `strcoll`의 호출과 동일한 결과를 냅니다.  `strcoll` 및 `stricoll`와 마찬가지로, `strxfrm`은 자동으로 멀티 바이트 문자열을 적절하게 처리합니다.  
  
 `wcsxfrm`는 `strxfrm`의 와이드 문자 버전이며, `wcsxfrm`의 문자열 인수는 와이드 문자 포인터입니다.  `wcsxfrm`의 경우, 문자열 변환 이후, 변형된 문자열 두 개를 사용한 `wcscmp`의 호출은 두 원본 문자열을 적용한 `wcscoll`의 호출과 동일한 결과를 냅니다.  `wcsxfrm` 및 `strxfrm` 는 동일하게 작동합니다.  `wcsxfrm`는 로캘 종속적인 동작에 현재 로캘을 사용합니다. `_wcsxfrm_l`는 현재 로캘 대신에 전달된 로캘을 사용합니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  `strSource`가 null 포인터 또는 `strDest`가 null 포인터\(카운트가 0이 아닌 경우\)인 경우, 또는 `count`가 `INT_MAX` 이상일 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `INT_MAX`을 반환합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsxfrm`|`strxfrm`|`strxfrm`|`wcsxfrm`|  
|`_tcsxfrm_l`|`_strxfrm_l`|`_strxfrm_l`|`_wcsxfrm_l`|  
  
 "C" 로케일에서 문자 집합\(ASCII 문자 집합\)의 순서는 사전적 문자 순서와 같습니다.  그러나 다른 로캘에서 문자 집합의 순서는 사전적 순서와 다를 수 있습니다.  예를 들어 특정 유럽 로캘에서, 문자 'a' \(값 0x61\) 앞 문자 '&\#x00E4;'\(값 0xE4\)의 값은 문자 집합, 그러나 사전 순으로 문자를 제외한 문자 'ä' 앞에 'a' 입니다.  
  
 문자 집합과 사전적 문자 순서가 다른 로캘에서는, 현재 로캘의 `LC_COLLATE` 범주 설정을 따르는 사전적 문자열 비교를 위하여 원본 문자열에서 `strxfrm`를 사용하고 결과 문자열에서 `strcmp` 문자열을 사용합니다.  따라서, 위의 로캘에서 사전순으로 두 문자열을 비교하기 위해서는, `strxfrm`를 원본 문자열에, `strcmp`를 결과 문자열에 사용합니다.  또는, 원본 문자열에 `strcmp` 대신 `strcoll`를 사용할 수 있습니다.  
  
 `strxfrm`은 기본적으로 `LCMAP_SORTKEY`를 이용한 [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) 래퍼입니다.  
  
 다음 식의 값은 원본 문자열의 `strxfrm` 변환을 저장하기 위한 배열의 크기입니다.  
  
```  
1 + strxfrm( NULL, string, 0 )  
```  
  
 오직 "C" 로캘에서, `strxfrm`는 다음과 같습니다.  
  
```  
strncpy( _string1, _string2, _count );  
return( strlen( _string1 ) );  
```  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strxfrm`|\<string.h\>|  
|`wcsxfrm`|\<string.h\> 또는 \<wchar.h\>|  
|`_strxfrm_l`|\<string.h\>|  
|`_wcsxfrm_l`|\<string.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)