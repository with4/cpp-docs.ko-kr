---
title: "_mbsnbcat, _mbsnbcat_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbcat_l"
  - "_mbsnbcat"
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
  - "mbsnbcat"
  - "mbsnbcat_l"
  - "_mbsnbcat"
  - "_mbsnbcat_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbcat 함수"
  - "_mbsnbcat_l 함수"
  - "_tcsncat 함수"
  - "_tcsncat_l 함수"
  - "mbsnbcat 함수"
  - "mbsnbcat_l 함수"
  - "tcsncat 함수"
  - "tcsncat_l 함수"
ms.assetid: aa0f1d30-0ddd-48d1-88eb-c6884b20fd91
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# _mbsnbcat, _mbsnbcat_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

덧붙여서, 최대추가, 다른 멀티 바이트 문자 문자열을 한 바이트의 첫 `n` 바이트입니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_mbsnbcat\_s, \_mbsnbcat\_s\_l](../../c-runtime-library/reference/mbsnbcat-s-mbsnbcat-s-l.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
unsigned char *_mbsnbcat(  
   unsigned char *dest,  
   const unsigned char *src,  
   size_t count   
);  
unsigned char *_mbsnbcat_l(  
   unsigned char *dest,  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
unsigned char *_mbsnbcat(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count   
); // C++ only  
template <size_t size>  
unsigned char *_mbsnbcat_l(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 `dest`  
 멀티 바이트 문자 대상 null로 끝나는 문자열입니다.  
  
 `src`  
 멀티 바이트 문자 소스 null로 끝나는 문자열입니다.  
  
 `count`  
 이 `src` 로 부터 `dest`로 덧붙여지는 바이트의 숫자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `_mbsnbcat` 은 목적지 문자열에 대한 포인터를 반환합니다.  반환 값 없음은 오류를 나타내는 데 예약되어 있습니다.  
  
## 설명  
 이 `_mbsnbcat` 함수는 `src` 의 바이트의 `count` 에서 `dest` 로 최대한 덧붙입니다.  이 `dest` 의 null 문자가 즉시 선행하는 바이트가 읽어진 바이트인 경우, `src` 의 초기 바이트는 읽어진 바이트에 덮어씁니다.  그렇지 않으면, `src` 의 초기 바이트는 `dest` 의 null 종결 문자 로 덮어씁니다.  이 `count` 바이트가 덧붙여지기전, null 바이트가 `src` 에 발생하는 경우, \_`mbsnbcat` 은 null 문자를 추가한 `src`로 부터 모든 바이트를 덧붙입니다.  이 `count` 이 `src`의 길이보다 큰 경우, `count` 장소에 `src` 이 사용됩니다.  결과 문자열은 null 문자로 종결됩니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  함수가 사용하는 로캘 종속 동작을 위한 현재 로캘의 `_mbsnbcat` 버전; `_mbsnbcat_l` 버전은 대신에 통과한 로캘 매기 변수를 사용하는 동일한 예외입니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 **보안 정보** 는 null로 끝나는 문자열을 사용 합니다.  Null로 끝나는 문자열 대상 버퍼의 크기를 초과할 수 없습니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
 여기 `dest` 혹은 `src` 이 `NULL`인 경우, 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)로 설명된 잘못된 매개 변수 오류를 생성할 겁니다.  오류가 처리가된 경우, 함수는 `EINVAL` 을 반환하고 `errno` 을 `EINVAL` 으로 설정합니다.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsncat`|[strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|`_mbsnbcat`|[wcsncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|  
|`_tcsncat_l`|`_strncat_l`|`_mbsnbcat_l`|`_wcsncat_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbsnbcat`|\<mbstring.h\>|  
|`_mbsnbcat_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_strncnt, \_wcsncnt, \_mbsnbcnt, \_mbsnbcnt\_l, \_mbsnccnt, \_mbsnccnt\_l](../../c-runtime-library/reference/strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)   
 [\_mbsnbcpy, \_mbsnbcpy\_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [\_mbsnbicmp, \_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [\_mbsnbcat\_s, \_mbsnbcat\_s\_l](../../c-runtime-library/reference/mbsnbcat-s-mbsnbcat-s-l.md)