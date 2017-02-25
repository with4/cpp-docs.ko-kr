---
title: "_ltoa, _ltow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ltoa"
  - "_ltow"
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
apitype: "DLLExport"
f1_keywords: 
  - "ltow"
  - "_ltot"
  - "_ltoa"
  - "_ltow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ltoa 함수"
  - "_ltow 함수"
  - "정수 변환"
  - "숫자 변환, 문자열로"
  - "정수(Long)를 문자열로 변환"
  - "ltoa 함수"
  - "ltow 함수"
ms.assetid: 14036104-2c25-4759-87c0-918ed8521e47
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _ltoa, _ltow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

long 정수를 문자열로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_ltoa\_s, \_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)를 참조하십시오.  
  
## 구문  
  
```  
char *_ltoa(  
   long value,  
   char *str,  
   int radix   
);  
wchar_t *_ltow(  
   long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ltoa(  
   long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ltow(  
   long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### 매개 변수  
 `value`  
 변환될 수 있는 숫자  
  
 `str`  
 문자열 결과  
  
 `radix`  
 `value` 의 기본  
  
## 반환 값  
 각 함수들은 `str`에 포인터를 반환합니다.  반환되는 오류가 없습니다.  
  
## 설명  
 `_ltoa` 함수는 `value` 의 숫자를 null로 끝나는 문자 문자열로 변환하고 결과\(최대 33바이트 까지\)를 `str` 에 저장합니다.  `radix` 인수는 `value` 의 기본을 지정합니다. 이 범위는 2에서 36 까지 입니다.  만일 `radix` 이 10 및 `value` 가 음수이면 저장된 문자열의 첫 문자는 빼기 기호 \( \)입니다.  `_ltow` 는 `_ltoa` 의 와이드 문자 버전입니다. `_ltow` 의 두 번째 인수와 반환 값은 와이드 문자 문자열입니다.  이러한 각 함수는 Microsoft 지정입니다.  
  
> [!IMPORTANT]
>  버퍼 오버런을 방지 하기 위해 , `str` 버퍼가 변환된 숫자와 후행 null 문자 및 기호 문자를 저장 하기에 충분 한지 확인해야 합니다.  
  
 C\+\+에서는 이러한 함수 템플릿 오버 로드 되어 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ltoa`|\<stdlib.h\>|  
|`_ltow`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [\_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)