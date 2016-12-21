---
title: "_strninc, _wcsninc, _mbsninc, _mbsninc_l | Microsoft Docs"
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
  - "_mbsninc"
  - "_mbsninc_l"
  - "_wcsninc"
  - "_strninc"
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
  - "strninc"
  - "wcsninc"
  - "mbsninc_l"
  - "_strninc"
  - "_tcsninc"
  - "mbsninc"
  - "_mbsninc_l"
  - "_ftcsninc"
  - "_wcsninc"
  - "_mbsninc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsninc 함수"
  - "_mbsninc_l 함수"
  - "_strninc 함수"
  - "_tcsninc 함수"
  - "_wcsninc 함수"
  - "mbsninc 함수"
  - "mbsninc_l 함수"
  - "strninc 함수"
  - "tcsninc 함수"
  - "wcsninc 함수"
ms.assetid: 6caace64-f9e4-48c0-afa8-ea51824ad723
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strninc, _wcsninc, _mbsninc, _mbsninc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`n` 문자마다 문자열 포인터를 이동  
  
> [!IMPORTANT]
>  `_mbsninc` 와 `_mbsninc_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *_strninc(  
   const char *str,  
   size_t count   
);  
wchar_t *_wcsninc(  
   const wchar_t *str,  
   size_t count   
);  
unsigned char *_mbsninc(  
   const unsigned char *str,  
   size_t count   
);  
unsigned char *_mbsninc(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `str`  
 소스 문자열입니다.  
  
 `count`  
 문자열 포인터를 증가 시킬 문자 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 이러한 각각의 루틴은 포인터를 `str` 에 반환합니다. `str` 은 `count` 문자 또는 `NULL` 에의 해 증가된 후이며, 제공된 포인터는 `NULL`일 경우입니다.  만일 `count` 는 `str`의 문자 수보다 크거나 같으면 결과는 정의되지 않습니다.  
  
## 설명  
 `_mbsninc` 증가 함수는 `str` 은 `count` 멀티 바이트 문자입니다.  `_mbsninc` 멀티 바이트 문자 시퀀스에 따라 인식된 [멀티 바이트 코드 페이지](../../c-runtime-library/code-pages.md) 에서 현재 사용 중입니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsninc`|`_strninc`|`_mbsninc`|`_wcsninc`|  
  
 `_strninc` 및 `_wcsninc` 는 byte–character 단일 문자열 및 와이드 문자 문자열 버전인 `_mbsninc` 입니다.  `_wcsninc` 및 `_strninc` 는 매핑 경우에 제공 되고 그렇지 않으면 사용할 수 없습니다.  자세한 내용은 [제네릭 텍스트 매핑 사용](../../c-runtime-library/using-generic-text-mappings.md) 및 [제네릭 텍스트 매핑](../../c-runtime-library/generic-text-mappings.md) 을 참조하십시오.  
  
 `_mbsninc_l` 는 전달된 로캘을 사용한다는 점을 제외하고 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbsninc`|\<mbstring.h\>|  
|`_mbsninc_l`|\<mbstring.h\>|  
|`_strninc`|\<tchar.h\>|  
|`_wcsninc`|\<tchar.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strdec, \_wcsdec, \_mbsdec, \_mbsdec\_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [\_strinc, \_wcsinc, \_mbsinc, \_mbsinc\_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [\_strnextc, \_wcsnextc, \_mbsnextc, \_mbsnextc\_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)