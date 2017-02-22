---
title: "_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strnextc"
  - "_mbsnextc_l"
  - "_mbsnextc"
  - "_wcsnextc"
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
  - "strnextc"
  - "tcsnextc"
  - "_mbsnextc_l"
  - "_mbsnextc"
  - "mbsnextc_l"
  - "ftcsnextc"
  - "mbsnextc"
  - "_tcsnextc"
  - "_wcsnextc"
  - "_ftcsnextc"
  - "_strnextc"
  - "wcsnextc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnextc 함수"
  - "_mbsnextc_l 함수"
  - "_strnextc 함수"
  - "_tcsnextc 함수"
  - "_wcsnextc 함수"
  - "mbsnextc 함수"
  - "mbsnextc_l 함수"
  - "strnextc 함수"
  - "tcsnextc 함수"
  - "wcsnextc 함수"
ms.assetid: e3086173-9eb5-4540-a23a-5d866bd05340
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에서 다음 문자를 찾습니다.  
  
> [!IMPORTANT]
>  `_mbsnextc` 와 `_mbsnextc_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
unsigned int _strnextc(  
   const char *str  
);  
unsigned int _wscnextc(  
   const wchar_t *str  
);   
unsigned int _mbsnextc(  
   const unsigned char *str   
);  
unsigned int _mbsnextc_l(  
   const unsigned char *str,  
   _locale_t locale  
);  
  
```  
  
#### 매개 변수  
 `str`  
 소스 문자열입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 각각 이러한 함수는 다음 문자의 `str`*.* 인 정수 값을 반환합니다.  
  
## 설명  
 이 `_mbsnextc` 함수는 문자열 포인터를 이동하지 않고 `str` 인 다음 멀티 바이트 문자의 정수 값을 반환합니다.  `_mbsnextc` 멀티 바이트 문자 시퀀스에 따라 인식된 [멀티 바이트 코드 페이지](../../c-runtime-library/code-pages.md) 에서 현재 사용 중입니다.  
  
 `str`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 함수는 0을 반환합니다.  
  
 **보안 정보** 이 API 버퍼 오버런 문제에 대한 상태로 잠재적인 위협을 초래합니다.  버퍼 오버런 문제는 자주 사용되는 시스템 공격 방법으로, 불필요한 권한 상승을 초래합니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsnextc`|`_strnextc`|`_mbsnextc`|`_wcsnextc`|  
  
 `_strnextc` 및 `_wcsnextc` 는 byte–character 단일 문자열 및 와이드 문자 문자열 버전인 `_mbsnextc` 입니다.  `_wcsnextc` 는 `string` 의 다음 와이드 문자의 정수 값을 반환합니다; `_strnextc` 는 `string` 의 다음 단일 문자의 정수 값을 반환합니다.  `_strnextc` 및 `_wcsnextc` 는 매핑 경우에 제공 되고 그렇지 않으면 사용할 수 없습니다.  자세한 내용은 [제네릭 텍스트 매핑 사용](../../c-runtime-library/using-generic-text-mappings.md) 및 [제네릭 텍스트 매핑](../../c-runtime-library/generic-text-mappings.md) 을 참조하십시오.  
  
 `_mbsnextc_l` 는 전달된 로캘을 사용한다는 점을 제외하고 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbsnextc`|\<mbstring.h\>|  
|`_mbsnextc_l`|\<mbstring.h\>|  
|`_strnextc`|\<tchar.h\>|  
|`_wcsnextc`|\<tchar.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strdec, \_wcsdec, \_mbsdec, \_mbsdec\_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [\_strinc, \_wcsinc, \_mbsinc, \_mbsinc\_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [\_strninc, \_wcsninc, \_mbsninc, \_mbsninc\_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)