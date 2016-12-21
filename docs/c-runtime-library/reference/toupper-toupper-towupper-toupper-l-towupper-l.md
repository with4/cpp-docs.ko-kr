---
title: "toupper, _toupper, towupper, _toupper_l, _towupper_l | Microsoft Docs"
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
  - "_toupper_l"
  - "towupper"
  - "toupper"
  - "_towupper_l"
  - "_toupper"
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
  - "towupper"
  - "_toupper"
  - "_totupper"
  - "toupper"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_totupper 함수"
  - "_toupper 함수"
  - "_toupper_l 함수"
  - "_towupper_l 함수"
  - "대/소문자, 변환"
  - "문자, 변환"
  - "문자열 변환, 대/소문자"
  - "문자열 변환, 다른 문자로"
  - "totupper 함수"
  - "toupper 함수"
  - "toupper_l 함수"
  - "towupper 함수"
  - "towupper_l 함수"
  - "대문자, 문자열 변환"
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# toupper, _toupper, towupper, _toupper_l, _towupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

대문자로 문자를 변환합니다.  
  
## 구문  
  
```  
int toupper(  
   int c   
);  
int _toupper(  
   int c   
);  
int towupper(  
   wint_t c   
);  
int _toupper_l(  
   int c ,  
   _locale_t locale  
);  
int _towupper_l(  
   wint_t c ,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 변환할 문자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 만일 가능한 경우, 각각의 이러한 루틴은 `c` 의 복사본으로 변환하고 결과를 반환합니다.  
  
 만일 `c` 가 `iswlower` 이 0이 아닌 와이드 문자 인 경우, `iswupper` 이 0이 아는 와이드 문자에 해당되며, `towupper` 이 해당하는 와이드 문자를 반환합니다; 그렇지 않으면, `towupper` 는 변경되지 않은 `c` 을 반환합니다.  
  
 오류를 나타내도록 예약된 반환 값은 존재하지 않습니다.  
  
 `toupper` 가 기대 결과를 제공하기 위해서, [\_\_isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md)와 [islower](../../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md) 는 모두 0이 아닌 수를 반환해야 합니다.  
  
## 설명  
 이러한 루틴 각각은 주어진 소문자를 가능하거나 적합한 대문자로 변환합니다.  `towupper`의 변환 사례는 특정 로캘에 국한됩니다.  이 경우 현재 로캘에 관련된 문자만이 변경됩니다.  `_l`  접미사가 없는 함수는 현재 설정된 로캘을 사용합니다.  `_l`  접미사를 가진 이러한 함수 버전은 로캘을 매개 변수로서 받고 현재 설정된 로캘 대신 그것을 사용합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 `toupper`가 기대 결과를 제공하기 위해서, [\_\_isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md)와 [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md)는 모두 0이 아닌 수를 반환해야 합니다.  
  
 [데이터 변환 루틴](../../c-runtime-library/data-conversion.md)  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_totupper`|`toupper`|`_mbctoupper`|`towupper`|  
|`_totupper_l`|`_toupper_l`|`_mbctoupper_l`|`_towupper_l`|  
  
> [!NOTE]
>  `_toupper_l` 및 `_towupper_l` 는 로캘 종속성 없고 직접 호출할 수 없습니다.  이는 `_totupper_l` 을 사용하면서 내부에 제공됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`toupper`|\<ctype.h\>|  
|`_toupper`|\<ctype.h\>|  
|`towupper`|\<ctype.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [to Functions](../../c-runtime-library/to-functions.md)의 예제를 참조하세요.  
  
## 해당 .NET Framework 항목  
 [System::Char::ToUpper](https://msdn.microsoft.com/en-us/library/system.char.toupper.aspx)  
  
## 참고 항목  
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)   
 [to 함수](../../c-runtime-library/to-functions.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)