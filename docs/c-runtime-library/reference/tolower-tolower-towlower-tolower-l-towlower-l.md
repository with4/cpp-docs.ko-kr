---
title: "tolower, _tolower, towlower, _tolower_l, _towlower_l | Microsoft Docs"
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
  - "_tolower_l"
  - "towlower"
  - "tolower"
  - "_tolower"
  - "_towlower_l"
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
  - "_totlower"
  - "tolower"
  - "_tolower"
  - "towlower"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tolower 함수"
  - "_tolower_l 함수"
  - "_totlower 함수"
  - "_towlower_l 함수"
  - "대/소문자, 변환"
  - "문자, 변환"
  - "소문자, 변환"
  - "문자열 변환, 대/소문자"
  - "문자열 변환, 다른 문자로"
  - "tolower 함수"
  - "tolower_l 함수"
  - "totlower 함수"
  - "towlower 함수"
  - "towlower_l 함수"
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tolower, _tolower, towlower, _tolower_l, _towlower_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자를 소문자로 변환합니다.  
  
## 구문  
  
```  
int tolower(  
   int c   
);  
int _tolower(  
   int c   
);  
int towlower(  
   wint_t c   
);  
int _tolower_l(  
   int c,  
   _locale_t locale   
);  
int _towlower_l(  
   wint_t c,  
   _locale_t locale   
);  
```  
  
#### 매개 변수  
 \[in\] `c`  
 변환할 문자입니다.  
  
 \[in\] `locale`  
 특정 로캘 번역에 사용하는 로캘입니다.  
  
## 반환 값  
 이러한 루틴 각각은 변환이 가능한 경우 `c`의 복사본을 소문자로 변환하고 결과를 반환합니다.  오류를 나타내도록 예약된 반환 값은 존재하지 않습니다.  
  
## 설명  
 이러한 루틴 각각은 가능하거나 관련 있는 경우 주어진 대문자를 소문자로 변환합니다.  `towlower`의 변환 사례는 특정 로캘에 국한됩니다.  이 경우 현재 로캘에 관련된 문자만이 변경됩니다.  `_l` 접미사가 없는 함수는 현재 설정된 로캘을 사용합니다.  `_l` 접미사를 가진 이러한 함수 버전은 로캘을 매개 변수로서 받고 현재 설정된 로캘 대신 그것을 사용합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 `_tolower`가 기대 결과를 제공하기 위해서, [\_\_isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md)와 [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md)는 모두 0이 아닌 수를 반환해야 합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_totlower`|`tolower`|`_mbctolower`|`towlower`|  
|`_totlower_l`|`_tolower_l`|`_mbctolower_l`|`_towlower_l`|  
  
> [!NOTE]
>  `_tolower_l` 및 `_towlower_l` 는 로캘 종속성 없고 직접 호출할 수 없습니다.  이는 `_totlower_l` 을 사용하면서 내부에 제공됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`tolower`|\<ctype.h\>|  
|`_tolower`|\<ctype.h\>|  
|`towlower`|\<ctype.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [to Functions](../../c-runtime-library/to-functions.md)의 예제를 참조하세요.  
  
## 해당 .NET Framework 항목  
 [System::Char::ToLower](https://msdn.microsoft.com/en-us/library/system.char.tolower.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)   
 [to 함수](../../c-runtime-library/to-functions.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)