---
title: "_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow | Microsoft Docs"
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
  - "_itow"
  - "_i64tow"
  - "_itoa"
  - "_i64toa"
  - "_ui64toa"
  - "_ui64tow"
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
  - "_i64tow"
  - "ui64toa"
  - "ui64tow"
  - "itot"
  - "_itot"
  - "_i64toa"
  - "_itoa"
  - "_itow"
  - "_ui64tow"
  - "i64toa"
  - "i64tow"
  - "itow"
  - "_ui64toa"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_i64toa 함수"
  - "_i64tow 함수"
  - "_itoa 함수"
  - "_itot 함수"
  - "_itow 함수"
  - "_ui64toa 함수"
  - "_ui64tow 함수"
  - "정수 변환"
  - "숫자 변환, 문자열로"
  - "i64toa 함수"
  - "i64tow 함수"
  - "정수, 변환"
  - "itoa 함수"
  - "itot 함수"
  - "itow 함수"
  - "ui64toa 함수"
  - "ui64tow 함수"
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 정수로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_itoa\_s, \_i64toa\_s, \_ui64toa\_s, \_itow\_s, \_i64tow\_s, \_ui64tow\_s](../../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)를 참조하십시오.  
  
## 구문  
  
```  
char *_itoa(  
   int value,  
   char *str,  
   int radix   
);  
char *_i64toa(  
   __int64 value,  
   char *str,  
   int radix   
);  
char * _ui64toa(  
   unsigned _int64 value,  
   char *str,  
   int radix   
);  
wchar_t * _itow(  
   int value,  
   wchar_t *str,  
   int radix   
);  
wchar_t * _i64tow(  
   __int64 value,  
   wchar_t *str,  
   int radix   
);  
wchar_t * _ui64tow(  
   unsigned __int64 value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_itoa(  
   int value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
char *_i64toa(  
   __int64 value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
char * _ui64toa(  
   unsigned _int64 value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _itow(  
   int value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _i64tow(  
   __int64 value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _ui64tow(  
   unsigned __int64 value,  
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
 다음 `value`의 기본은; 범위 2–36에 있어야 합니다.  
  
## 반환 값  
 각 함수들은 `str`에 포인터를 반환합니다.  반환되는 오류가 없습니다.  
  
## 설명  
 다음 `_itoa`, `_i64toa`, 및 `_ui64toa` 함수는 주어진 `value` 인수의 자리를 는 null로 끝나는 문자열로 변경하고, `str`에서 결과\( `_itoa` 에 대한 최대 33, `_i64toa` 에 대한 65 및 `_ui64toa`\)를 저장합니다.  만일 `radix` 이 10 및 `value` 가 음수이면 저장된 문자열의 첫 문자는 빼기 기호 \( `–` \)입니다.  다음 `_itow`, `_i64tow`, 및 `_ui64tow` 는 각각 `_itoa`, `_i64toa`, 및 `_ui64toa`의 와이드 문자 버전입니다.  
  
> [!IMPORTANT]
>  버퍼 오버런을 방지 하기 위해 , `str` 버퍼가 변환된 숫자와 후행 null 문자 및 기호 문자를 저장 하기에 충분 한지 확인해야 합니다.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_itot`|`_itoa`|`_itoa`|`_itow`|  
|`_i64tot`|`_i64toa`|`_i64toa`|`_i64tow`|  
|`_ui64tot`|`_ui64toa`|`_ui64toa`|`_ui64tow`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_itoa`|\<stdlib.h\>|  
|`_i64toa`|\<stdlib.h\>|  
|`_ui64toa`|\<stdlib.h\>|  
|`_itow`|\<stdlib.h\>|  
|`_i64tow`|\<stdlib.h\>|  
|`_ui64tow`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_itoa.c  
// compile with: /W3  
// This program makes use of the _itoa functions  
// in various examples.  
  
#include <string.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char buffer[65];  
   int r;  
   for( r=10; r>=2; --r )  
   {  
     _itoa( -1, buffer, r ); // C4996  
     // Note: _itoa is deprecated; consider using _itoa_s instead  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
   printf( "\n" );  
   for( r=10; r>=2; --r )  
   {  
     _i64toa( -1L, buffer, r ); // C4996  
     // Note: _i64toa is deprecated; consider using _i64toa_s  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
   printf( "\n" );  
   for( r=10; r>=2; --r )  
   {  
     _ui64toa( 0xffffffffffffffffL, buffer, r ); // C4996  
     // Note: _ui64toa is deprecated; consider using _ui64toa_s  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
}  
```  
  
  **기본 10:\-1 \(2 자\)**  
**기본 9:12068657453 \(11 자\)**  
**기본 8:37777777777 \(11 자\)**  
**기본 7:211301422353 \(12 자\)**  
**기본 6:1550104015503 \(13 자\)**  
**기본 5:32244002423140 \(14 자\)**  
**기본 4:3333333333333333 \(16 자\)**  
**기본 3:102002022201221111210 \(21 자\)**  
**기본 2:11111111111111111111111111111111 \(32 자\)**  
**기본 10:\-1 \(2 자\)**  
**기본 9:145808576354216723756 \(21 자\)**  
**기본 8:1777777777777777777777 \(22 자\)**  
**기본 7:45012021522523134134601 \(23 자\)**  
**기본 6:3520522010102100444244423 \(25 자\)**  
**기본 5:2214220303114400424121122430 \(28 자\)**  
**기본 4:33333333333333333333333333333333 \(32 자\)**  
**기본 3:11112220022122120101211020120210210211220 \(41 자\)**  
**기본 2:1111111111111111111111111111111111111111111111111111111111111111 \(64 자\)**  
**기본 10:18446744073709551615 \(20 자\)**  
**기본 9:145808576354216723756 \(21 자\)**  
**기본 8:1777777777777777777777 \(22 자\)**  
**기본 7:45012021522523134134601 \(23 자\)**  
**기본 6:3520522010102100444244423 \(25 자\)**  
**기본 5:2214220303114400424121122430 \(28 자\)**  
**기본 4:33333333333333333333333333333333 \(32 자\)**  
**기본 3:11112220022122120101211020120210210211220 \(41 자\)**  
**기본 2:1111111111111111111111111111111111111111111111111111111111111111 \(64 자\)**   
## 해당 .NET Framework 항목  
 [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [\_ltoa, \_ltow](../../c-runtime-library/reference/ltoa-ltow.md)   
 [\_ltoa\_s, \_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [\_ultoa\_s, \_ultow\_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md)