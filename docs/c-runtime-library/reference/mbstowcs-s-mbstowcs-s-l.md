---
title: "mbstowcs_s, _mbstowcs_s_l | Microsoft Docs"
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
  - "_mbstowcs_s_l"
  - "mbstowcs_s"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbstowcs_s_l"
  - "mbstowcs_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbstowcs_s_l 함수"
  - "mbstowcs_s 함수"
  - "mbstowcs_s_l 함수"
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
caps.latest.revision: 31
caps.handback.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mbstowcs_s, _mbstowcs_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멀티 바이트 문자의 시퀀스를 해당하는 와이드 문자의 시퀀스로 변환합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) 버전입니다.  
  
## 구문  
  
```  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count   
);  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `pReturnValue`  
 변환 된 문자 수입니다.  
  
 \[out\] `wcstr`  
 변환 된 와이드 문자의 결과에 대한 문자열 버퍼의 주소입니다.  
  
 \[in\] `sizeInWords`  
 단어에서 `wcstr` 버퍼의 크기입니다.  
  
 \[in\]`mbstr`  
 종료된 멀티 바이트 문자 null 의 시퀀스의 주소입니다.  
  
 \[in\] `count`  
 null 종결 문자 또는 [\_TRUNCATE](../../c-runtime-library/truncate.md) 를 포함하지 않는 `wcstr` 버퍼에 저장하기 위한 와이드 문자의 최대 수입니다.  
  
 \[in\] `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
|오류 조건|반환 값과 `errno`|  
|-----------|-------------------|  
|`wcstr` 는 `NULL` 및 `sizeInWords` \> 0 입니다.|`EINVAL`|  
|`mbstr`가 `NULL`인 경우|`EINVAL`|  
|대상 버퍼가 너무 작아 변환 된 문자열을 포함할 수 없습니다. \( `count` 가 `_TRUNCATE` 가 아닌 한, 아래 설명 참조\)|`ERANGE`|  
|`wcstr` 는 `NULL` 및 `sizeInWords` \=\= 0 이 아닙니다.|`EINVAL`|  
  
 이러한 조건이 발생 하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 설명된 대로 잘못 된 매개 변수 예외를 호출합니다.  실행이 계속 되도록 혀용된 경우, 함수는 오류 코드를 반환하고 `errno` 를 테이블에 표시 된 대로 설정합니다.  
  
## 설명  
 `mbstowcs_s` 함수는 멀티 바이트 문자열이 `wcstr`가 가리키는 버퍼에 저장되는 와이드 문자로 `mbstr` 때문에 조준 변환합니다.  이러한 조건 중 하나가 충족 될 때까지 변환은 문자마다 계속합니다.  
  
-   멀티 바이트 null 문자는 발견됩니다.  
  
-   잘못 된 멀티 바이트 문자가 발견 됩니다.  
  
-   `wcstr` 에 저장된 와이드 문자의 수는 `count` 와 동일합니다.  
  
 대상 문자열은 항상 null로 끝납니다. \(오류의 경우에도\)  
  
 `count`가 특별한 값 [\_TRUNCATE](../../c-runtime-library/truncate.md) 인 경우, null 종료의 여지가 남겨진 동안 대상 버퍼에 맞도록 `mbstowcs_s` 는 많은 문자열을 변환합니다.  
  
 만일 `mbstowcs_s` 가 성공적으로 소스 문자열을 변환하는 경우, 이것은 null 종결자를 포함한 변환된 문자열의 와이드 문자열의 크기를 `*``pReturnValue` 로 넣습니다.\( `NULL`가 아닌 `pReturnValue` 를 제공합니다.\)  `wcstr` 인수는 `NULL` 이고 필요한 버퍼 크기를 결정하는 방법을 제공하는 경우에도 발생합니다.  `wcstr` 가 `NULL` 인 경우, `count` 는 무시되고 `sizeInWords` 는 0이 됩니다.  
  
 `mbstowcs_s` 가 잘못된 멀티 바이트 문자를 발견하는 경우, `*``pReturnValue` 에 0을 넣고, 대상 버퍼에 빈 문자열을 설정하고 `errno` 를 `EILSEQ` 로 설정하고 `EILSEQ` 를 반환합니다.  
  
 만일 `mbstr` 와 `wcstr` 에 의해 가르켜진 시퀀스가 겹쳐질 경우, `mbstowcs_s` 의 동작은 정의되지 않습니다.  
  
> [!IMPORTANT]
>  되도록 `wcstr` 및 `mbstr` 가 겹치지 않도록 하고, `count` 가 변환할 멀티바이트 문자의 수를 올바르게 반영하도록 합니다.  
  
 `mbstowcs_s` 는 로캘 종속 동작에 대해 현재 로캘을 사용 합니다. `_mbstowcs_s_l` 는 대신에 전달 된 로캘을 사용 하는 것을 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`mbstowcs_s`|\<stdlib.h\>|  
|`_mbstowcs_s_l`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)