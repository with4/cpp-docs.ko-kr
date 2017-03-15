---
title: "_ultoa_s, _ultow_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ultow_s"
  - "_ultoa_s"
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
  - "_ultow_s"
  - "ultoa_s"
  - "ultow_s"
  - "_ultoa_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ultoa_s 함수"
  - "_ultow_s 함수"
  - "정수 변환"
  - "숫자 변환, 문자열로"
  - "정수, 변환"
  - "ultoa_s 함수"
  - "ultow_s 함수"
ms.assetid: 606ce905-6752-46ac-a15a-bdc22920e1d4
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _ultoa_s, _ultow_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부호 없는 long 정수를 문자열로 변환합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md) 버전입니다.  
  
## 구문  
  
```  
errno_t _ultoa_s(  
    unsigned long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ultow_s(  
    unsigned long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ultoa_s(  
    unsigned long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ultow_s(  
    unsigned long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### 매개 변수  
 `value`  
 변환될 수 있는 숫자  
  
 `str`  
 문자열 결과  
  
 `sizeOfstr`  
 `_ultoa_s`를 위한 `str`의 바이트 단위 또는 `_ultow_s`의 단어의 크기입니다.  
  
 `radix`  
 `value` 의 기본  
  
## 반환 값  
 함수가 성공하면 0, 그렇지 않으면 오류 코드입니다.  
  
## 설명  
 `_ultoa_s` 함수는 `value` 의 숫자를 null로 끝나는 문자 문자열로 변환하고 결과\(최대 33바이트 까지\)를 `str` 에 저장합니다.  `radix` 인수는 `value` 의 기본을 지정합니다. 이 범위는 2에서 36 까지 입니다.  `_ultow_s`는 `_ultoa_s`의 와이드 문자 버전이며, `_ultow_s`에 대한 두 번째 인수는 와이드 문자 문자열입니다.  
  
 만일 `str`가 `NULL` 포인터이거나 `sizeOfstr`이 0보다 적거나 같은 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개변수 처리기가 호출됩니다.  함수의 실행이 계속되도록 허용되는 경우, 이러한 함수는 \-1을 반환하고 `errno`를 `EINVAL` 로 설정하거나 만약 `value` 또는 `str`이 long 정수의 범위를 벗어나는 경우, 이러한 함수는 \-1을 반환하고 `errno`을 `ERANGE`로 설정합니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_ultot_s`|`_ultoa_s`|`_ultoa_s`|`_ultow_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ultoa_s`|\<stdlib.h\>|  
|`_ultow_s`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [\_ltoa, \_ltow](../../c-runtime-library/reference/ltoa-ltow.md)   
 [\_ltoa\_s, \_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)   
 [\_ltoa\_s, \_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)