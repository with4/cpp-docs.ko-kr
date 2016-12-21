---
title: "_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l | Microsoft Docs"
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
  - "_ismbclower"
  - "_ismbclower_l"
  - "_ismbcupper_l"
  - "_ismbcupper"
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
  - "_ismbcupper"
  - "_ismbclower"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbclower 함수"
  - "_ismbclower_l 함수"
  - "_ismbcupper 함수"
  - "_ismbcupper_l 함수"
  - "ismbclower 함수"
  - "ismbclower_l 함수"
  - "ismbcupper 함수"
  - "ismbcupper_l 함수"
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멀티 바이트 문자는 대 \/ 소문자 여부를 검사 합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _ismbclower(  
   unsigned int c   
);  
int _ismbclower_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcupper(  
   unsigned int c   
);  
int _ismbcupper_l(  
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
|`_ismbclower`|소문자 알파벳|0이 아닌 경우를 반환 하는 경우에만 `c` 표현 싱글바이트 ASCII 소문자 영어 글자: 0x61\<\=`c`\<\= 0x7A.|  
|`_ismbclower_l`|소문자 알파벳|0이 아닌 경우를 반환 하는 경우에만 `c` 표현 싱글바이트 ASCII 소문자 영어 글자: 0x61\<\=`c`\<\= 0x7A.|  
|`_ismbcupper`|대문자 알파벳|0이 아닌 경우를 반환 하는 경우에만 `c` 표현 싱글바이트 ASCII 소문자 영어 글자: 0x61\<\=`c`\<\= 0x7A.|  
|`_ismbcupper_l`|대문자 알파벳|0이 아닌 경우를 반환 하는 경우에만 `c` 표현 싱글바이트 ASCII 소문자 영어 글자: 0x61\<\=`c`\<\= 0x7A.|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ismbclower`|\<mbstring.h\>|  
|`_ismbclower_l`|\<mbstring.h\>|  
|`_ismbcupper`|\<mbstring.h\>|  
|`_ismbcupper_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
  
-   [System::Char::IsLower](https://msdn.microsoft.com/en-us/library/system.char.islower.aspx)  
  
-   [System::Char::IsUpper](https://msdn.microsoft.com/en-us/library/system.char.isupper.aspx)  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [\_ismbc 루틴](../../c-runtime-library/ismbc-routines.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)