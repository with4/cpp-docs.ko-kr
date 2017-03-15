---
title: "_mbccpy_s, _mbccpy_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbccpy_s"
  - "_mbccpy_s_l"
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
  - "_mbccpy_s_l"
  - "mbccpy_s_l"
  - "mbccpy_s"
  - "_mbccpy_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbccpy_s 함수"
  - "_mbccpy_s_l 함수"
  - "_tccpy_s 함수"
  - "_tccpy_s_l 함수"
  - "mbccpy_s 함수"
  - "mbccpy_s_l 함수"
  - "tccpy_s 함수"
  - "tccpy_s_l 함수"
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# _mbccpy_s, _mbccpy_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에서 다른 문자열을 멀티 바이트 문자를 복사합니다.  이러한 버전의 [\_mbccpy, \_mbccpy\_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
errno_t _mbccpy_s(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src   
);  
errno_t _mbccpy_s_l(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
);  
template <size_t size>  
errno_t _mbccpy_s(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src   
); // C++ only  
template <size_t size>  
errno_t _mbccpy_s_l(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `dest`  
 대상에 복사 합니다.  
  
 \[in\] `buffSizeInBytes`  
 대상 버퍼의 크기입니다.  
  
 \[out\] `pCopied`  
 바이트 복사 \(1 또는 2 성공\)의 수로 채워집니다.  숫자가 신경쓰지 않는 경우 `NULL` 를 통과시키세요.  
  
 \[in\] `src`  
 멀티 바이트 문자를 복사 합니다.  
  
 \[in\] `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  여기 `src` 혹은 `dest` 이 `NULL` 인 경우, 혹은 `dest`가 복사된 `buffSizeinBytes` 바이트가 보다 많은 경우, 그러면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)로 묘사되어 잘못된 매개 변수 처리기는 호출합니다.  계속해서 실행하도록 허용된 경우, 이 함수는 `EINVAL` 를 반환하고 `errno` 은 `EINVAL`으로 설정합니다.  
  
## 설명  
 `_mbccpy_s` 함수는 하나의 멀티 바이트 문자를 `src` 에서 `dest`까지 복사합니다.  이 `src` 은 [\_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md)를 명백하게 호출함으로써 결정된 멀티 바이트 문자의 선행 바이트를 가리키지 않는 경우, 그러면 `src` 을 가리키는 단일 바이트는 복사됩니다.  이 `src` 선행 문자열을 가리키나 따르는 바이트가 0 혹은 잘못된 경우에, 0은 `dest`으로 복사되고, `errno` 은 `EILSEQ` 으로 설정되고, 함수는 `EILSEQ`을 반환합니다.  
  
 이 `_mbccpy_s` 은 null 종결자를 추가하지 않습니다; 그러나, `src` 이 null 문자를 가리키는 경우, 그러면 null은 `dest` \(일반 싱글바이트 복사본이 됩니다\) 가 복사됩니다.  
  
 이 `pCopied` 인 값은 복사된 바이트의 숫자로 채워집니다.  작업이 성공한 경우 가능한 값은 1과 2 입니다.  이 `NULL` 가 전달된 경우, 매개 변수는 무시됩니다.  
  
|`src`|이 `dest` 로 복사합니다.|`pCopied`|반환 값|  
|-----------|-----------------------|---------------|----------|  
|non\-lead\-byte|non\-lead\-byte|1|0|  
|0|0|1|0|  
|0이 아님을 따르는 선행 바이트|0이 아님을 따르는 선행 바이트|2|0|  
|0을 따르는 선행 바이트|0|1|`EILSEQ`|  
  
 두번째 행이 단지 특별한 첫번째의 경우를 참고하세요.  또한 표가 `buffSizeInBytes` \>\= `pCopied` 을 참고하세요.  
  
 `_mbccpy_s`는 로캘 종속 동작의 현재 로캘을 사용합니다.  `_mbccpy_s_l` 는 `_mbccpy_s` 와 동일합니다. 여기서 `_mbccpy_s_l` 모든 로캘 종속 동작에 대해 전달 된 로캘을 사용하는것을 제외합니다.  
  
 C\+\+에서는 이러한 함수를 사용하는 것은 템플릿 오버로드에 의해 단순화됩니다; 오버로드는 자동으로 버퍼의 길이를 추정할수 있고, 크기 인수를 지정할 필요를 없앱니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tccpy_s`|매크로 또는 인라인 함수에 매핑.|`_mbccpy_s`|매크로 또는 인라인 함수에 매핑.|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbccpy_s`|\<mbstring.h\>|  
|`_mbccpy_s_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 참고 항목  
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)