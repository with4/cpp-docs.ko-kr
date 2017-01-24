---
title: "_ultoa, _ultow | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ultoa"
  - "_ultow"
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
  - "ultot"
  - "ultow"
  - "_ultoa"
  - "_ultow"
  - "_ultot"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ultoa 함수"
  - "_ultot 함수"
  - "_ultow 함수"
  - "정수 변환"
  - "숫자 변환, 문자열로"
  - "정수, 변환"
  - "ultot 함수"
  - "ultow 함수"
ms.assetid: 7a472dc4-5652-4513-93c3-3358522c23be
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ultoa, _ultow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부호 없는 long 정수를 문자열로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_ultoa\_s, \_ultow\_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md)를 참조하십시오.  
  
## 구문  
  
```  
char *_ultoa(  
   unsigned long value,  
   char *str,  
   int radix   
);  
wchar_t *_ultow(  
   unsigned long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ultoa(  
   unsigned long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ultow(  
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
  
 `radix`  
 `value` 의 기본입니다*.*  
  
## 반환 값  
 각 함수들은 `str`에 포인터를 반환합니다.  반환되는 오류가 없습니다.  
  
## 설명  
 `_ultoa` 함수는 `value`를 null로 끝나는 문자 문자열로 변환하고 결과\(최대 33바이트 까지\)를 `str` 에 저장합니다.  오버플로 검사는 수행하지 않습니다.  `radix`는 `value`의 기본을 지정합니다. `radix`는 반드시 2 – 36의 범위에 있어야 합니다.  `_ultow` 는 `_ultoa` 의 와이드 문자 버전입니다.  
  
> [!IMPORTANT]
>  버퍼 오버런을 방지하기 위해 , `str` 버퍼가 변환된 숫자와 후행 null 문자를 저장하기에 충분한지 확인해야 합니다.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_ultot`|`_ultoa`|`_ultoa`|`_ultow`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ultoa`|\<stdlib.h\>|  
|`_ultow`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [\_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)