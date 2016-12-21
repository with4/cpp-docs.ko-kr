---
title: "_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l | Microsoft Docs"
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
  - "_ismbcalpha"
  - "_ismbcalnum"
  - "_ismbcdigit"
  - "_ismbcalnum_l"
  - "_ismbcdigit_l"
  - "_ismbcalpha_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ismbcdigit"
  - "ismbcalnum_l"
  - "_ismbcdigit_l"
  - "_ismbcalpha"
  - "ismbcalnum"
  - "ismbcdigit"
  - "ismbcalpha"
  - "_ismbcalnum_l"
  - "_ismbcalnum"
  - "ismbcdigit_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbcalnum 함수"
  - "_ismbcalnum_l 함수"
  - "_ismbcalpha 함수"
  - "_ismbcalpha_l 함수"
  - "_ismbcdigit 함수"
  - "_ismbcdigit_l 함수"
  - "ismbcalnum 함수"
  - "ismbcalnum_l 함수"
  - "ismbcalpha 함수"
  - "ismbcalpha_l 함수"
  - "ismbcdigit 함수"
  - "ismbcdigit_l 함수"
ms.assetid: 12d57925-aebe-46e0-80b0-82b84c4c31ec
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멀티 바이트 문자는 영숫자, 알파, 또는 숫자가 문자를 확인 합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _ismbcalnum  
(  
   unsigned int c   
);  
int _ismbcalnum_l  
(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcalpha  
(  
   unsigned int c   
);  
int _ismbcalpha_l  
(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcdigit  
(  
   unsigned int c   
);  
int _ismbcdigit_l  
(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 문자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 이러한 각 루틴은 이 문자가 테스트 조건을 만족하는 경우 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다.  `c`\<\= 255 및 해당 하는 `_ismbb` 루틴인 경우 \(예를 들어, `_ismbcalnum` 에 반응하는 `_ismbbalnum`\), 결과는 `_ismbb` 루틴에 응답하는 반환값 입니다.  
  
## 설명  
 이러한 각 함수는 지정한 조건에 대해 주어진 멀티바이트 문자를 테스트합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
|루틴|테스트 조건|932 코드 페이지 예제|  
|--------|------------|-------------------|  
|`_ismbcalnum,_ismbcalnum_l`|영, 숫자|0이 아닌 경우를 반환 하는 경우에만 `c` 는 영어 ASCII 문자의 싱글바이트 표시: 예제를 참조 하십시오 `_ismbcdigit` 및 `_ismbcalpha`.|  
|`_ismbcalpha,_ismbcalpha_l`|Alphabetic|0이 아닌 경우 및 경우에만 반환 `c` 는 영어 ASCII 문자의 싱글바이트 표시: 되었습니다\<\=`c`\<0x61 0x5A \=\<\=`c`\<\= 0x7A; 또는 가타카나 문자: 0xA6\<\=`c`\<\= 0xDF.|  
|`_ismbcdigit,_ismbcdigit`|\_DIGIT|0이 아닌 경우를 반환 하는 경우에만 `c` 는 ASCII 숫자는 1 바이트 표현: 0x30\<\=`c`\<0x39 \=.|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ismbcalnum,_ismbcalnum_l`|\<mbstring.h\>|  
|`_ismbcalpha,_ismbcalpha_l`|\<mbstring.h\>|  
|`_ismbcdigit,_ismbcdigit_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
  
-   [System::Char::IsLetter](https://msdn.microsoft.com/en-us/library/system.char.isletter.aspx)  
  
-   [System::Char::IsDigit](https://msdn.microsoft.com/en-us/library/system.char.isdigit.aspx)  
  
-   `_ismbcalnum`에는 적용되지 않습니다. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [\_ismbc 루틴](../../c-runtime-library/ismbc-routines.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)