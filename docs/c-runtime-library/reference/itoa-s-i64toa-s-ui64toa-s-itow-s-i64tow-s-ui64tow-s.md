---
title: "_itoa_s, _i64toa_s, _ui64toa_s, _itow_s, _i64tow_s, _ui64tow_s | Microsoft Docs"
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
  - "_ui64tow_s"
  - "_itoa_s"
  - "_itow_s"
  - "_ui64toa_s"
  - "_i64tow_s"
  - "_i64toa_s"
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
  - "i64tot_s"
  - "itow_s"
  - "_ui64tow_s"
  - "_itow_s"
  - "ui64tot_s"
  - "_ui64toa_s"
  - "itoa_s"
  - "_i64tow_s"
  - "_i64tot_s"
  - "_itot_s"
  - "_i64toa_s"
  - "_itoa_s"
  - "ui64toa_s"
  - "i64toa_s"
  - "_ui64tot_s"
  - "i64tow_s"
  - "itot_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_i64toa_s 함수"
  - "_i64tot_s 함수"
  - "_i64tow_s 함수"
  - "_itoa_s 함수"
  - "_itot_s 함수"
  - "_itow_s 함수"
  - "_ui64toa_s 함수"
  - "_ui64tot_s 함수"
  - "_ui64tow_s 함수"
  - "정수 변환"
  - "숫자 변환, 문자열로"
  - "i64toa_s 함수"
  - "i64tow_s 함수"
  - "정수, 변환"
  - "itoa_s 함수"
  - "itow_s 함수"
  - "ui64toa_s 함수"
ms.assetid: eb746581-bff3-48b5-a973-bfc0a4478ecf
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _itoa_s, _i64toa_s, _ui64toa_s, _itow_s, _i64tow_s, _ui64tow_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 정수로 변환합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md) 버전입니다.  
  
## 구문  
  
```  
errno_t _itoa_s(  
   int value,  
   char *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _i64toa_s(  
   __int64 value,  
   char *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _ui64toa_s(  
   unsigned _int64 value,  
   char *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _itow_s(  
   int value,  
   wchar_t *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _i64tow_s(  
   __int64 value,  
   wchar_t *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _ui64tow_s(  
   unsigned __int64 value,  
   wchar_t *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
template <size_t size>  
errno_t _itoa_s(  
   int value,  
   char (&buffer)[size],  
   int radix   
); // C++ only  
template <size_t size>  
errno_t _itow_s(  
   int value,  
   wchar_t (&buffer)[size],  
   int radix   
); // C++ only  
```  
  
#### 매개 변수  
 \[in\] `value`  
 변환될 수 있는 숫자  
  
 \[out\] `buffer`  
 변환의 결과로 채워집니다.  
  
 \[in\] `sizeInCharacters`  
 단일 바이트 문자들 또는 와이드 문자들의 버퍼의 크기.  
  
 \[in\] `radix`  
 다음 `value`의 기본은; 범위 2–36에 있어야 합니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  만약 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 것 처럼 다음과 같은 조건들 중 하나가 적용되는 경우 그 함수는 잘못된 매개변수 처리기를 불러일으킵니다.  
  
### 오류 조건  
  
|값|버퍼|문자의 사이즈|radix|반환|  
|-------|--------|-------------|-----------|--------|  
|any|`NULL`|any|any|`EINVAL`|  
|any|any|\<\=0|any|`EINVAL`|  
|any|any|\<필요한 문자열 결과의 길이|any|`EINVAL`|  
|any|any|any|`radix` \< 2 또는 `radix` \> 36|`EINVAL`|  
  
 **보안 문제**  
  
 이런 함수들은 만약 `buffer` 가 올바른 메모리를 가리키지 않고`NULL`이 아닐 때, 또는 버퍼의 길이가 결과 문자열을 보유할 수 있을 정도로 길지 않은 경우 액세스 위반 발생할 수 있습니다.  
  
## 설명  
 매개 변수 및 반환 값을 제외하고 `_itoa_s` 함수들은 해당되지 않는 보안 버전들과 같은 동작을 합니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_itot_s`|`_itoa_s`|`_itoa_s`|`_itow_s`|  
|`_i64tot_s`|`_i64toa_s`|`_i64toa_s`|`_i64tow_s`|  
|`_ui64tot_s`|`_ui64toa_s`|`_ui64toa_s`|`_ui64tow_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_itoa_s`|\<stdlib.h\>|  
|`_i64toa_s`|\<stdlib.h\>|  
|`_ui64toa_s`|\<stdlib.h\>|  
|`_itow_s`|\<stdlib.h\> 또는 \<wchar.h\>|  
|`_i64tow_s`|\<stdlib.h\> 또는 \<wchar.h\>|  
|`_ui64tow_s`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_itoa_s.c  
#include <stdlib.h>  
#include <string.h>  
  
int main( void )  
{  
    char buffer[65];  
    int r;  
    for( r=10; r>=2; --r )  
    {  
       _itoa_s( -1, buffer, 65, r );  
       printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
    }  
    printf( "\n" );  
    for( r=10; r>=2; --r )  
    {  
       _i64toa_s( -1L, buffer, 65, r );  
       printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
    }  
    printf( "\n" );  
    for( r=10; r>=2; --r )  
    {  
       _ui64toa_s( 0xffffffffffffffffL, buffer, 65, r );  
       printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
    }  
}  
```  
  
## Output  
  
```  
base 10: -1 (2 chars)  
base 9: 12068657453 (11 chars)  
base 8: 37777777777 (11 chars)  
base 7: 211301422353 (12 chars)  
base 6: 1550104015503 (13 chars)  
base 5: 32244002423140 (14 chars)  
base 4: 3333333333333333 (16 chars)  
base 3: 102002022201221111210 (21 chars)  
base 2: 11111111111111111111111111111111 (32 chars)  
  
base 10: -1 (2 chars)  
base 9: 145808576354216723756 (21 chars)  
base 8: 1777777777777777777777 (22 chars)  
base 7: 45012021522523134134601 (23 chars)  
base 6: 3520522010102100444244423 (25 chars)  
base 5: 2214220303114400424121122430 (28 chars)  
base 4: 33333333333333333333333333333333 (32 chars)  
base 3: 11112220022122120101211020120210210211220 (41 chars)  
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)  
  
base 10: 18446744073709551615 (20 chars)  
base 9: 145808576354216723756 (21 chars)  
base 8: 1777777777777777777777 (22 chars)  
base 7: 45012021522523134134601 (23 chars)  
base 6: 3520522010102100444244423 (25 chars)  
base 5: 2214220303114400424121122430 (28 chars)  
base 4: 33333333333333333333333333333333 (32 chars)  
base 3: 11112220022122120101211020120210210211220 (41 chars)  
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)  
```  
  
## 해당 .NET Framework 항목  
 [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [\_ltoa, \_ltow](../../c-runtime-library/reference/ltoa-ltow.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)