---
title: "_strinc, _wcsinc, _mbsinc, _mbsinc_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsinc"
  - "_wcsinc"
  - "_mbsinc_l"
  - "_strinc"
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
  - "mbsinc_l"
  - "_strinc"
  - "strinc"
  - "_mbsinc"
  - "_wcsinc"
  - "wcsinc"
  - "mbsinc"
  - "_mbsinc_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsinc 함수"
  - "_mbsinc_l 함수"
  - "_strinc 함수"
  - "_tcsinc 함수"
  - "_wcsinc 함수"
  - "mbsinc 함수"
  - "mbsinc_l 함수"
  - "strinc 함수"
  - "tcsinc 함수"
  - "wcsinc 함수"
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strinc, _wcsinc, _mbsinc, _mbsinc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열 포인터를 한 문자씩 이동합니다.  
  
> [!IMPORTANT]
>  `_mbsinc` 및 `_mbsinc_l`은 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
char *_strinc(    const char *current,    _locale_t locale ); wchar_t *_wcsinc(    const wchar_t *current,    _locale_t locale ); unsigned char *_mbsinc(    const unsigned char *current  ); unsigned char *_mbsinc_l(    const unsigned char *current,    _locale_t locale );   
```  
  
#### 매개 변수  
 `current`  
 문자 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 이러한 각 루틴은 `current` 바로 뒤에 오는 문자로 포인터를 반환합니다.  
  
## 설명  
 `_mbsinc` 함수는 `current` 바로 뒤에 오는 멀티바이트 문자의 첫 번째 바이트로 포인터를 반환합니다.  `_mbsinc` 함수는 현재 사용 중인 [멀티바이트 코드 페이지](../../c-runtime-library/code-pages.md)에 따라 멀티바이트 문자 시퀀스를 인식하고 `_mbsinc_l`은 전달된 로캘 매개 변수를 대신 사용한다는 점을 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 Tchar.h에 정의된 제네릭 텍스트 함수인 `_tcsinc`는 `_MBCS`가 정의된 경우 `_mbsinc`로 매핑되고 `_UNICODE`가 정의된 경우 `_wcsinc`로 매핑됩니다.  그렇지 않으면 `_tcsinc`는 `_strinc`로 매핑됩니다.  `_strinc` 및 `_wcsinc`는 `_mbsinc`의 싱글바이트 문자 및 와이드 문자 버전입니다.  `_strinc` 및 `_wcsinc`는 이러한 매핑을 위해서만 제공되고 그 외에는 사용하면 안 됩니다.  자세한 내용은 [일반 텍스트 매핑 사용](../../c-runtime-library/using-generic-text-mappings.md) 및 [일반 텍스트 매핑](../../c-runtime-library/generic-text-mappings.md)를 참조하십시오.  
  
 `current`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용한 경우 이 함수는 `EINVAL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
> [!IMPORTANT]
>  이러한 함수는 버퍼 오버런 위협에 노출될 수 있습니다.  버퍼 오버런은 불필요한 권한 상승을 발생시킬 수 있으므로 시스템 공격에 사용될 수 있습니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbsinc`|\<mbstring.h\>|  
|`_mbsinc_l`|\<mbstring.h\>|  
|`_strinc`|\<tchar.h\>|  
|`_wcsinc`|\<tchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strdec, \_wcsdec, \_mbsdec, \_mbsdec\_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [\_strnextc, \_wcsnextc, \_mbsnextc, \_mbsnextc\_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)   
 [\_strninc, \_wcsninc, \_mbsninc, \_mbsninc\_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)