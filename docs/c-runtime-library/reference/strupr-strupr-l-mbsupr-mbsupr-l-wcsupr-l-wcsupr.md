---
title: "_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsupr_l"
  - "_mbsupr"
  - "_strupr_l"
  - "_wcsupr"
  - "_wcsupr_l"
  - "_strupr"
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
  - "ntoskrnl.exe"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbsupr"
  - "_ftcsupr"
  - "mbsupr"
  - "_tcsupr"
  - "strupr_l"
  - "_fstrupr"
  - "_strupr"
  - "mbsupr_l"
  - "_wcsupr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstrupr 함수"
  - "_ftcsupr 함수"
  - "_mbsupr 함수"
  - "_mbsupr_l 함수"
  - "_strupr 함수"
  - "_strupr_l 함수"
  - "_tcsupr 함수"
  - "_tcsupr_l 함수"
  - "_wcsupr 함수"
  - "_wcsupr_l 함수"
  - "대/소문자 변환, CRT 함수"
  - "fstrupr 함수"
  - "ftcsupr 함수"
  - "mbsupr 함수"
  - "mbsupr_l 함수"
  - "문자열 변환[C++], 대/소문자"
  - "문자열[C++], 대/소문자"
  - "문자열[C++], 대/소문자 변환"
  - "strupr 함수"
  - "strupr_l 함수"
  - "tcsupr 함수"
  - "tcsupr_l 함수"
  - "대문자, 문자열 변환"
  - "wcsupr 함수"
  - "wcsupr_l 함수"
ms.assetid: caac8f16-c233-41b6-91ce-575ec7061b77
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# _strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 대문자로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  `_mbsupr` 와 `_mbsupr_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *_strupr(  
   char *str   
);  
wchar_t *_wcsupr(  
   wchar_t *str   
);  
unsigned char *_mbsupr(  
   unsigned char *str   
);  
char *_strupr_l(  
   char *str,  
   _locale_t locale  
);  
wchar_t *_wcsupr_l(  
   wchar_t *str,  
   _locale_t locale  
);  
unsigned char *_mbsupr_l(  
   unsigned char *str,  
   _locale_t locale  
);  
template <size_t size>  
char *_strupr(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wcsupr(  
   wchar_t (&str)[size]  
); // C++ only  
template <size_t size>  
unsigned char *_mbsupr(  
   unsigned char (&str)[size]  
); // C++ only  
template <size_t size>  
char *_strupr_l(  
   char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
wchar_t *_wcsupr_l(  
   wchar_t (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
unsigned char *_mbsupr_l(  
   unsigned char (&str)[size],  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 `str`  
 대문자로 시작할 문자열입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 변경된 문자열에 대한 포인터를 반환합니다.  수정이 위치에서 완료되었기 때문에 반환 된 포인터는 입력 인수로 전달 된 포인터와 동일합니다  반환 값 없음은 오류를 나타내는 데 예약되어 있습니다.  
  
## 설명  
 `_strupr` 함수는 위치에서 `str` 의 각 소문자를 대문자로 변환합니다.  변환은 로캘의 `LC_CTYPE` 범주 설정에 의해 결정됩니다.  다른 문자는 영향을 받지 않습니다.  `LC_CTYPE` 에 대한 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 를 참조하십시오.  `_l` 접미사가 없는 이러한 함수의 버전은 현재 로캘을 사용합니다; `_l` 접미사가 있는 버전은 대신 전달된 로캘을 사용한다는 것을 제외하고는 같습니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 `_wcsupr` 및 `_mbsupr` 는 와이드 문자와 `_strupr`의 멀티 바이트 문자 버전입니다.  인수와 `_wcsupr` 의 반환 값은 와이드 문자 문자열입니다; `_mbsupr` 은 멀티 바이트 문자 문자열입니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 `str` 가 NULL 포인터인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개 변수 처리기가 호출 됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 본래의 문자열을 반환하고 `errno` 를 `EINVAL` 로 설정합니다.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsupr`|`_strupr`|`_mbsupr`|`_wcsupr`|  
|`_tcsupr_l`|`_strupr_l`|`_mbsupr_l`|`_wcsupr_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strupr`, `_strupr_l`|\<string.h\>|  
|`_wcsupr`, `_wcsupr_l`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbsupr`, `_mbsupr_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 [strtod](../../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::String::ToUpper](https://msdn.microsoft.com/en-us/library/system.string.toupper.aspx)  
  
## 참고 항목  
 [로캘](../../c-runtime-library/locale.md)   
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strlwr, \_wcslwr, \_mbslwr, \_strlwr\_l, \_wcslwr\_l, \_mbslwr\_l](../../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)