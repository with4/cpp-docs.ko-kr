---
title: "_mbsnbcat_s, _mbsnbcat_s_l | Microsoft Docs"
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
  - "_mbsnbcat_s_l"
  - "_mbsnbcat_s"
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
  - "_mbsnbcat_s"
  - "mbsnbcat_s"
  - "_mbsnbcat_s_l"
  - "mbsnbcat_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbcat_s 함수"
  - "_mbsnbcat_s_l 함수"
  - "_tcsncat 함수"
  - "_tcsncat_s_l 함수"
  - "mbsnbcat_s 함수"
  - "mbsnbcat_s_l 함수"
  - "tcsncat 함수"
  - "tcsncat_s_l 함수"
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbcat_s, _mbsnbcat_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멀티바이트 문자열을 최소한 다른 멀티바이트 문자열의 첫 번째 `n`바이트에 추가합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)의 버전입니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
errno_t _mbsnbcat_s(  
   unsigned char *dest,  
   size_t sizeInBytes,  
   const unsigned char *src,  
   size_t count   
);  
errno_t _mbsnbcat_s_l(  
   unsigned char *dest,  
   size_t sizeInBytes,  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _mbsnbcat_s(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsnbcat_s_l(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 `dest`  
 null로 끝나는 멀티바이트 문자 대상 문자열입니다.  
  
 `sizeInBytes`  
 `dest` 버퍼의 크기\(바이트\)입니다.  
  
 `src`  
 null로 끝나는 멀티바이트 문자 소스 문자열입니다.  
  
 `Count`  
 `dest`에 추가할 `src`의 바이트 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공하면 0이고, 그렇지 않으면 오류 코드입니다.  
  
### 오류 조건  
  
|`Dest`|`sizeInBytes`|`src`|반환 값|  
|------------|-------------------|-----------|----------|  
|`NULL`|모두|모두|`EINVAL`|  
|모두|\<\= 0|모두|`EINVAL`|  
|모두|모두|`NULL`|`EINVAL`|  
  
 오류 조건이 발생하는 경우 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 오류를 발생시킵니다.  오류가 처리되면 함수는 `EINVAL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## 설명  
 `_mbsnbcat_s` 함수는 `dest`에 최소한 `count`의 첫 번째 `src` 바이트를 추가합니다.  `dest`에서 null 문자 바로 앞에 오는 바이트가 선행 바이트인 경우 해당 바이트는 `src`의 초기 바이트에 의해 덮어쓰여집니다.  그렇지 않으면 `src`의 초기 바이트가 `dest`의 null 종결 문자를 덮어씁니다.  `src` 바이트가 추가되기 전에 `count`에 null 바이트가 나타나는 경우 \_`_mbsnbcat_s`는 `src`의 모든 바이트를 null 바이트까지 추가합니다.  `count`가 `src`의 길이보다 크면 `src`의 길이가 `count` 대신 사용됩니다.  결과 문자열은 null 문자로 끝납니다.  중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요.  `_l` 접미사가 없는 함수는 현재 로캘을 사용하고 `_l` 접미사가 있는 함수는 전달된 로캘 매개 변수를 대신 사용한다는 점을 제외하고 이러한 함수의 버전은 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 C\+\+에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 보다 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없어지고 보안 수준이 낮은 기존 함수를 보안 수준이 높은 최신 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsncat`|[strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|`_mbsnbcat_s`|[wcsncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|  
|`_tcsncat_s_l`|`_strncat_s_l`|`_mbsnbcat_s_l`|`_wcsncat_s_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbsnbcat_s`|\<mbstring.h\>|  
|`_mbsnbcat_s_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_strncnt, \_wcsncnt, \_mbsnbcnt, \_mbsnbcnt\_l, \_mbsnccnt, \_mbsnccnt\_l](../../c-runtime-library/reference/strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)   
 [\_mbsnbcpy, \_mbsnbcpy\_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [\_mbsnbcpy\_s, \_mbsnbcpy\_s\_l](../../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)   
 [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)